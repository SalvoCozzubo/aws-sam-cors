# Test Cors

This is a simple YAML template for testing CORS

## Instructions

1. `sam build`
2. `sam deploy` (or `--guided`)

## Example

### Fetch
```javascript
const params = {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({ action: 'beat', room: 1 }),
};

fetch('<url>', params)
    .then(response => response.json())
    .then(json => console.log('response', json))
    .catch(error => {
        console.error(error);
    });
```

### Beacon
```javascript
const body = { action: 'beat', room: 1 };
const headers = { 'Content-Type': 'application/json' };
const blob = new Blob([JSON.stringify(body)], headers);
navigator.sendBeacon('<url>',blob);
```