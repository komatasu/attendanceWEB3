# AttendanceVerification Smart Contract

## Overview

The `AttendanceVerification` smart contract is a Solidity-based contract designed for managing student attendance and rewards. It allows an administrator to record attendance, grant rewards, and manage administrative roles. The contract is implemented in Solidity version 0.8.0.

## Features

- **Attendance Recording**: Track student attendance on the blockchain.
- **Reward Management**: Grant and track rewards for students.
- **Admin Management**: Change the admin address when needed.

## Contract Structure

### State Variables

- **`admin`**: Address of the current administrator.
- **`attendanceCount`**: Mapping from student addresses to their attendance count.
- **`rewardBalance`**: Mapping from student addresses to their reward balance.

### Events

- **`AttendanceRecorded(address indexed student, uint256 timestamp)`**: Emitted when a student's attendance is recorded.
- **`RewardGranted(address indexed student, uint256 amount)`**: Emitted when a reward is granted to a student.

### Functions

- **`constructor()`**: Initializes the contract and sets the creator as the initial admin.
  
- **`modifier onlyAdmin()`**: Ensures that only the admin can call certain functions.

- **`recordAttendance(address student)`**: Records attendance for the specified student. Only callable by the admin.

- **`rewardStudent(address student, uint256 amount)`**: Grants a reward to the specified student. Only callable by the admin. The reward amount must be greater than zero.

- **`getAttendance(address student) view returns (uint256)`**: Retrieves the attendance count for the specified student.

- **`getRewardBalance(address student) view returns (uint256)`**: Retrieves the reward balance for the specified student.

- **`changeAdmin(address newAdmin)`**: Changes the admin address. Only callable by the current admin. The new admin address cannot be zero.

## Deployment

To deploy the `AttendanceVerification` contract:

1. **Prepare Your Environment**:
   - Ensure you have a Solidity-compatible development environment (e.g., [Remix](https://remix.ethereum.org/), [Truffle](https://www.trufflesuite.com/), or [Hardhat](https://hardhat.org/)).

2. **Compile the Contract**:
   - Use Solidity version 0.8.0 to compile the contract.

3. **Deploy the Contract**:
   - Deploy the contract to your desired Ethereum network (e.g., Rinkeby, Mainnet) using your preferred deployment tool.

## Usage

1. **Deploy the Contract**:
   - Deploy the `AttendanceVerification` contract using your deployment tool. The contract creator will be set as the initial admin.

2. **Record Attendance**:
   - The admin can call the `recordAttendance(address student)` function to record attendance for a student.

3. **Grant Rewards**:
   - The admin can call the `rewardStudent(address student, uint256 amount)` function to grant rewards to a student.

4. **Check Attendance and Rewards**:
   - Anyone can call `getAttendance(address student)` to view a student’s attendance count.
   - Anyone can call `getRewardBalance(address student)` to view a student’s reward balance.

5. **Change Admin**:
   - The current admin can call `changeAdmin(address newAdmin)` to update the admin address.

## Security Considerations

- **Admin Privileges**: Only grant admin access to trusted individuals, as they have control over attendance and rewards.
- **Admin Address Changes**: Be cautious when changing the admin address to prevent unauthorized access.

## License

This contract is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or issues, please contact the repository maintainer at [your-email@example.com](mailto:your-email@example.com).
