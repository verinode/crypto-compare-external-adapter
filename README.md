# CryptoCompare External Adapter For ChainLink

An external adapter to be used with AWS Lambda.

## Input Params

- `endpoint`: The endpoint to use (defaults to price)
- `fsym` or `coin`: The coin to ask for (required)
- `tsyms` or `market`: The currency to convert to (required)

## Output Example

```json
{
	"USD": 432.12
}
```

## Installation

```bash
npm install
```

## Testing

```bash
npm test
```

## How to Create a zip

```bash
zip -r crypto-compare-adapter.zip .
```

## Install to AWS Lambda

- In Lambda Functions, create function
- On the Create function page:
  - Give the function a name
  - Use Node.js 8.10 for the runtime
  - Choose an existing role or create a new one
  - Click Create Function
- Under Function code, select "Upload a .zip file" from the Code entry type drop-down
- Click Upload and select the `crypto-compare-adapter.zip` file
- Handler should remain index.handler
- Add the environment variable:
  - Key: API_KEY
  - Value: `Your API KEY`
- Save
