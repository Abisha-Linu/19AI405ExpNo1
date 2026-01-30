<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Abisha Linu L</h3>
<h3>Register Number: 212224040011</h3>


<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<h3>Theory:</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

## PROGRAM:
```
import random

class HealthMonitoringAgent:
    def __init__(self, sensors, actuators):
        self.sensors = sensors
        self.actuators = actuators
        self.performance = 0

    def run(self):
        for _ in range(5):  # Check 5 random rooms
            health_state = self.sensors.get_health_state()
            action = self.choose_action(health_state)
            self.actuators.perform_action(action)

            if action == "Prescribe medicine":
                self.performance += 1
            elif action == "Move to another room":
                self.performance -= 1

        print("Final Performance Score:", self.performance)

    def choose_action(self, health_state):
        if health_state['temperature'] > 38:
            return "Prescribe medicine"
        else:
            return "Move to another room"


class HealthSensors:
    def get_health_state(self):
        return {
            'temperature': random.uniform(36.0, 39.5),
            'location': random.randint(1, 10)
        }


class HealthActuators:
    def perform_action(self, action):
        print("Action:", action)


if __name__ == "__main__":
    sensors = HealthSensors()
    actuators = HealthActuators()

    agent = HealthMonitoringAgent(sensors, actuators)
    agent.run()
```
## OUTPUT:

<img width="316" height="143" alt="image" src="https://github.com/user-attachments/assets/860f0aed-c717-4357-a79b-050d8dc36f68" />

## RESULT:
Hence, the solution for the given AI problem is found.
