# glw/api-client

a PHP library for handling API requests using cURL. It supports GET, POST, PUT, DELETE, and UPDATE operations.

## Installation

You can install the library via Composer:

```bash
composer require glw/api-client
```

Configuration
Copy the .env.example to .env and set your API_URL and API_TOKEN:

```bash
API_URL=https://api.example.com
API_TOKEN=your_api_token_here
```

Example usage in PHP Native:

```php
require 'vendor/autoload.php';

use Glw\ApiClient\ApiClient;

$client = new ApiClient();

// GET request
$response = $client->get('/endpoint');

// POST request
$response = $client->post('/endpoint', ['key' => 'value']);

// PUT request
$response = $client->put('/endpoint', ['key' => 'value']);

// DELETE request
$response = $client->delete('/endpoint');

// UPDATE request
$response = $client->update('/endpoint', ['key' => 'value']);

echo json_encode($response);
```

Example usage in Laravel:

```php
namespace App\Http\Controllers;

use Glw\ApiClient\ApiClient;

class ApiController extends Controller
{
    public function index()
    {
        $client = new ApiClient();

        $response = $client->get('/track');
        return response()->json($response);
    }
}
```

Example usage in CodeIgneter:

```php
use Glw\ApiClient\ApiClient;

class ApiController extends CI_Controller
{
    public function index()
    {
        $client = new ApiClient();

        $response = $client->get('/track');
        echo json_encode($response);
    }
}
```