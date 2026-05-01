# Autonomous Mobile Robot Navigation for WATonomous

## Project Overview
This repository contains the software stack for an **Autonomous Mobile Robot** designed to navigate point-to-point in a simulated environment. The system integrates perception, mapping, and path planning to achieve obstacle-aware navigation using a differential drive platform.

## Key Engineering Features
*   **Perception & Mapping:** Developed **ROS2 nodes in C++** to process LiDAR and Odometry data into a dynamic **2D Costmap**.
*   **Path Planning:** Implemented the **A* Algorithm** to compute optimal, collision-free paths in real-time.
*   **Path Following:** Applied the **Pure Pursuit** controller for smooth trajectory tracking and differential drive motion control.
*   **Infrastructure:** Orchestrated a **Docker-based Monorepo** for seamless deployment and utilized **Foxglove** for real-time data visualization and debugging.

## 💻 System Prerequisites
To ensure reproducibility and ease of deployment, this project is fully containerized using **Docker**.

1.  **Supported OS:** Linux Ubuntu (>= 22.04), Windows (WSL2), or MacOS.
2.  **Container Engine:** [Docker Engine](https://docker.com) is required to run robotic modules without local library dependencies.

## Getting Started

### 1. Repository Setup
```bash
git clone git@github.com:WATonomous/wato_asd_training.git
cd wato_asd_training
```

### 2. Infrastructure Management
We utilize a custom Docker Compose wrapper (`./watod`) for orchestration.

*   **Setup Development Environment:**
    ```bash
    ./watod --setup-dev-env robot
    ```
*   **Build Modules:**
    ```bash
    ./watod build
    ```
*   **Launch System:**
    ```bash
    ./watod up
    ```

### 3. Visualization & Debugging
1.  Open **Foxglove** (Web or Desktop app).
2.  Click **Open Connection** and enter the URL provided in the terminal logs (e.g., `localhost:8765`).
3.  Import the pre-made layout: `config/wato_asd_training_foxglove_config.json`.

## Acknowledgments
- **Infrastructure:** WATonomous Monorepo Infrastructure.
- **Libraries:** ROS2 (rclcpp), nav_msgs, std_msgs.
