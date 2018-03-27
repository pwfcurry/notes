## Testing React/Redux with Enzyme

- Export both the plain and the connect components, and selectors if applicable. Don't test the connected component.

- If the plain component has nested connected components, it cannot be rendered via `mount` without first mocking the
 redux store. Instead render with `shallow` - this will not traverse into React components.
	- Don't call `.html` when shallow mounting - this fully mounts the component

- To test lifecycle methods (componentDidUpdate, componentDidMount etc) either `mount` or pass
 `{ lifecycleExperimental: true }` as the second parameter to `shallow`.

		const view = shallow(<Component>, { lifecycleExperimental: true });

- If you have to `mount` either pass the store in the `context` or use proxyquire and mock out the connected dependencies.

		const view = mount(<Component>, { context: { router: MockRouter } });
		
## Testing with Selenium

[Tips](http://elementalselenium.com/tips)

- When using `xpath(...)` make sure you're passing an xpath, not a css selector...

- `element.text` does not work on `<input>`, use `.attribute("value")` instead.

- When using the remote web driver, you may have to manually scroll to elements if they are not visible on the page -
 this isn't necessary when running locally.
 
 ### Updating chromedriver
 	sudo yarn global add chromedriver --prefix /usr/bin
 
