# Fitness Reward System Smart Contract

A Clarity smart contract that implements a comprehensive fitness rewards and achievement system on the Stacks blockchain. The system gamifies fitness activities by rewarding users with tokens and achievements for completing their fitness goals.

## About

The Fitness Reward System smart contract enables users to:
- Set personalized fitness goals
- Track activity progress
- Earn rewards for achieving goals
- Collect achievement badges
- Level up based on activities
- Participate in a blockchain-based fitness ecosystem

## Features

### User Management
- User registration system
- Profile tracking
- Activity history
- Level progression
- Achievement badges

### Goal System
- Create custom fitness goals
- Set activity targets
- Track progress
- Deadline management
- Multiple activity type support

### Reward System
- Dynamic reward calculation
- Secure reward distribution
- Achievement badges
- Points accumulation
- Level-based benefits

## Contract Architecture

### Core Components
1. User Profiles
   - Tracks user statistics and progress
   - Manages fitness points and levels
   - Records achievement history

2. Goal Management
   - Handles goal creation and tracking
   - Validates progress updates
   - Manages completion status

3. Reward Distribution
   - Calculates rewards based on goal difficulty
   - Manages reward pool
   - Handles secure distribution

## Usage

### Basic Implementation

1. Register a new user:
```clarity
(contract-call? .fitness-reward-system register-fitness-user)
```

2. Create a fitness goal:
```clarity
(contract-call? .fitness-reward-system create-fitness-goal
    u1000 ;; activity target
    u1672531200 ;; deadline (unix timestamp)
    "running" ;; activity type
)
```

3. Record activity:
```clarity
(contract-call? .fitness-reward-system record-fitness-activity
    u1 ;; goal ID
    u100 ;; activity amount
)
```

4. Claim rewards:
```clarity
(contract-call? .fitness-reward-system claim-goal-rewards u1)
```

## Functions Reference

### Public Functions

#### User Management
- `register-fitness-user`: Register new user
- `get-fitness-user-profile`: Get user profile details

#### Goal Management
- `create-fitness-goal`: Create new fitness goal
- `record-fitness-activity`: Log activity progress
- `get-fitness-goal-details`: Get goal details

#### Reward System
- `claim-goal-rewards`: Claim rewards for completed goals
- `get-fitness-contract-stats`: Get contract statistics

### Administrative Functions
- `add-fitness-reward-pool-funds`: Add funds to reward pool
- `transfer-contract-administration`: Transfer contract ownership

## Data Structures

### User Profile
```clarity
{
    fitness-points: uint,
    completed-activities-count: uint,
    fitness-level: uint,
    last-activity-timestamp: uint,
    total-rewards-claimed: uint,
    current-active-goals: uint
}
```

### Fitness Goal
```clarity
{
    activity-target: uint,
    current-progress: uint,
    goal-deadline: uint,
    is-goal-completed: bool,
    goal-reward-amount: uint,
    fitness-activity-type: string-ascii
}
```

## Security

### Security Features
- Owner-only administrative functions
- Input validation
- Balance checks
- Error handling
- Secure reward distribution
- Deadline enforcement

### Error Codes
- `ERR-UNAUTHORIZED-ACCESS` (u100)
- `ERR-DUPLICATE-USER-REGISTRATION` (u101)
- `ERR-USER-PROFILE-NOT-FOUND` (u102)
- `ERR-INVALID-FITNESS-GOAL` (u103)
- `ERR-INSUFFICIENT-REWARD-BALANCE` (u104)
- `ERR-INVALID-REWARD-AMOUNT` (u105)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Submit pull request