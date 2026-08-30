# Experiment 5 – CloudSim Simulation

## Title
Simulate a Cloud Scenario Using CloudSim

## Aim
To simulate a cloud scenario using CloudSim and run a scheduling algorithm.

> **Note:** The manual's aim mentions "a scheduling algorithm not present in CloudSim". However, the actual procedure documented in the manual demonstrates setting up Eclipse with CloudSim 3.0.3 and running the built-in **CloudSimExample1.java**. No custom scheduling algorithm is documented in the provided manual procedure. `CloudSimExample1.java` included here follows the official CloudSim 3.0.3 example.

---

## Requirements
| Item | Version / Details |
|------|------------------|
| IDE | Eclipse IDE for Java Developers (64-bit) |
| Framework | CloudSim 3.0.3 |
| Math Library | Apache Commons Math 3.6.1 |
| JDK | Java 7 or above |
| OS | Windows (64-bit) |

---

## Introduction to CloudSim
**CloudSim** is an open-source simulation toolkit developed at the CLOUDS Lab, University of Melbourne. It enables researchers and developers to model and simulate cloud computing infrastructure and services — including datacenters, virtual machines, cloudlets (tasks), and scheduling policies — without requiring actual cloud hardware.

Key components:
- **CloudSim Core** – event-driven simulation engine
- **Datacenter** – simulates physical cloud infrastructure
- **DatacenterBroker** – manages VM and cloudlet submission
- **Vm** – represents a virtual machine
- **Cloudlet** – represents a task/job to be executed

---

## Setup Procedure

### Step 1: Download Eclipse
- Download **Eclipse IDE for Java Developers (Windows 64-bit)** from [https://www.eclipse.org/](https://www.eclipse.org/)

### Step 2: Download CloudSim 3.0.3
- Download from the CloudSim GitHub releases or the CLOUDS Lab website.
- Extract the ZIP to a local folder (e.g., `C:\cloudsim-3.0.3\`).

### Step 3: Download Apache Commons Math
- Download `commons-math3-3.6.1.jar` from [https://commons.apache.org/](https://commons.apache.org/)

### Step 4: Open Eclipse and Import Project
1. Launch `eclipse.exe`
2. **File → New → Project → Java Project**
3. Project Name: `CloudSim`
4. Uncheck "Use default location" → Browse to `C:\cloudsim-3.0.3\`
5. Click **Finish**

### Step 5: Add External JAR (if required)
1. Right-click project → **Build Path → Configure Build Path**
2. **Libraries** tab → **Add External JARs**
3. Browse to `commons-math3-3.6.1.jar` → Open → **OK**

### Step 6: Run CloudSimExample1
1. Navigate to: `examples → org.cloudbus.cloudsim.examples`
2. Open: `CloudSimExample1.java`
3. Run: **Run → Run** or `Ctrl + F11`
4. View output in Eclipse Console.

---

## Source File

`CloudSimExample1.java` demonstrates:
- Initializing CloudSim
- Creating a Datacenter with 1 Host
- Creating a Broker
- Creating 1 Virtual Machine
- Creating 1 Cloudlet (task)
- Starting the simulation
- Printing the results table

---

## How to Execute
1. Set up Eclipse with CloudSim 3.0.3 as described above.
2. Place `CloudSimExample1.java` in the examples package.
3. Run using `Ctrl + F11` in Eclipse.
4. Observe output in the Eclipse Console window.

---

## Expected Output
```
Starting CloudSimExample1...
Initializing CloudSim...
Creating Datacenter...
Creating Broker...
Creating Virtual Machines...
Creating Cloudlets...
Starting CloudSim simulation...

========== OUTPUT ==========
Cloudlet ID    STATUS     Data Center ID  VM ID   Time    Start Time  Finish Time
0              SUCCESS    2               0       0.40    0.10        0.50

Simulation completed.
CloudSimExample1 finished!
```

---

## Files
| File | Description |
|------|-------------|
| `CloudSimExample1.java` | CloudSim simulation source code |
| `output.txt` | Simulated Eclipse console output |

---

## Result
The CloudSim scenario was successfully simulated using Eclipse. The datacenter, broker, virtual machine, and cloudlet were configured and the simulation output was observed in the Eclipse console.
