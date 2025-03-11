# MelodAI Auto Bot - AirdropInsiders

This script automates tasks and mining pool claims on the MelodAI platform using multiple accounts and optional proxy support.

## Features

- Fetch and complete tasks
- Claim rewards for completed tasks
- Manage mining pool claims
- Support for HTTP and SOCKS proxies
- Multi-account support

## Usage

### Run Modes

1. **Single Account Mode**: Manually input token and member ID.
2. **Multi Account Mode**: Load accounts from `accounts.txt` file.

### Configuration Files

- `accounts.txt`: List of accounts in `token|member_id` format.
- `proxies.txt`: List of proxies in `http://` or `socks4://` or `socks5://` format.

### Functions

- **readAccountsFromFile**: Reads accounts from a file.
  - **Parameters**: `filename`
  - **Returns**: Array of accounts

- **readProxies**: Reads proxies from a file.
  - **Parameters**: `filename`
  - **Returns**: Array of proxies

- **getProxyAgent**: Creates a proxy agent based on the proxy URL.
  - **Parameters**: `proxy`
  - **Returns**: Proxy agent or null

- **getTasks**: Fetches the task list for a given account.
  - **Parameters**: `token`, `member_id`, `proxy`, `log`
  - **Returns**: Array of tasks

- **completeTask**: Completes a specific task.
  - **Parameters**: `token`, `member_id`, `task_id`, `task_name`, `proxy`, `log`
  - **Returns**: Boolean indicating success

- **claimReward**: Claims the reward for a completed task.
  - **Parameters**: `token`, `member_id`, `task_id`, `task_name`, `proxy`, `log`
  - **Returns**: Reward amount

- **getMiningPoolCountdown**: Fetches the countdown time for the mining pool.
  - **Parameters**: `token`, `member_id`, `proxy`, `log`
  - **Returns**: Countdown time in seconds or -1 on failure

- **getUserCoin**: Fetches the user's coin and crystal balance.
  - **Parameters**: `token`, `member_id`, `proxy`, `log`
  - **Returns**: Object with `coin` and `crystal` properties

- **animateCountdown**: Animates a countdown in the console.
  - **Parameters**: `seconds`, `log`
  - **Returns**: Promise resolved after countdown

- **addMiningPool**: Adds a mining pool for the user.
  - **Parameters**: `token`, `member_id`, `proxy`, `log`
  - **Returns**: Object with `coin_id` and `receive_id` properties

- **claimMiningPoolDirect**: Claims the mining pool coin directly.
  - **Parameters**: `token`, `member_id`, `receive_id`, `coin_id`, `proxy`, `log`
  - **Returns**: Claimed amount

- **processAccount**: Processes tasks and mining pool claims for a single account.
  - **Parameters**: `token`, `member_id`, `proxies`
  - **Returns**: None

- **main**: Entry point of the script. Handles user input and starts the appropriate mode.
  - **Parameters**: None
  - **Returns**: None

## Examples

### Running the Script in Single Account Mode

```sh
node script.js
```

### Running the Script in Multi Account Mode

```sh
node script.js
```

Ensure `accounts.txt` and `proxies.txt` are properly formatted and placed in the same directory as the script.

## License

This project is licensed under the MIT License.