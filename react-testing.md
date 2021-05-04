## React jest testing

### Installation

```shell
$ yarn add -D @testing-library/react react-test-renderer jest ts-jest
```

### Steps

#### creating components

1. Add `data-testid` to refrence this id during tests instead of actual id

#### writing tests
1. It should render component without errors in dom.
1. It should unmount from dom without errors.
    ```javascript
    it("renders this element without errors", () => {
      const root = document.createElement("div");
      // rendering component
      ReactDOM.render(<YoutComponent />, root);
      // unmounting component
      ReactDOM.unmountComponentAtNode(root);
    });
    ```

1. It sould should render element correctly (_check by verifying pure attributes of an element_).
     - Check component attributes.
        ```javascript
        expect(getByTestId("youtElementId")).toHaveTextContent("test-2");
        ```
    - Check component attributes after changing state.