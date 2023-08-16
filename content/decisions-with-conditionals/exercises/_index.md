---
title: "Exercises: Booleans and Conditionals"
date: 2023-05-25T12:55:09-05:00
draft: false
weight: 2
originalAuthor: John Woolbright # to be set by page creator
originalAuthorGitHub: jwoolbright23 # to be set by page creator
reviewer: Sally Steuterman # to be set by the page reviewer
reviewerGitHub: gildedgardenia # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # Wed Jul 5 08:49:19 AM CDT 2023
---

Attempt these exercises to test your understanding. Don't worry if you struggle
while working on them. Struggling and then reviewing the material will help you
remember it.

Take note of any problem here or topic from this chapter that you don't understand. 
Take a break and return to the problem. Do you see it in a new way or have a better 
understanding? If not, try spending five minutes researching the topic. Start with this
book and if you still have questions, ask one on the internet or Slack/Discourse. 
You're not the first person to learn to code and you're definitely not the first person
to ask a question or get stuck!

1. **Declare and initialize the following variables for our space shuttle**

| Variable Name       | Value       |
|---------------------|-------------|
| engineIndicatorLight| red blinking|
| spaceSuitsOn        | true        |
| shuttleCabinReady   | true        |
| crewStatus          | spaceSuitsOn && shuttleCabinReady|
| computerStatusCode  | 200         |
| shuttleSpeed        | 15000       |

{{% expand "Check Your Solution" %}}
```javascript
let engineIndicatorLight = "red blinking";
let spaceSuitsOn = true;
let shuttleCabinReady = true;
let crewStatus = spaceSuitsOn && shuttleCabinReady;
let computerStatusCode = 200;
let shuttleSpeed = 15000;
```
{{% /expand %}}

2. **Examine the code below. What will be printed to the console?**

   Use the value of `engineIndicatorLight` defined above to answer this question.

   ```javascript
   if (engineIndicatorLight === "green") {
      console.log("engines have started");
   } else if (engineIndicatorLight === "green blinking") {
      console.log("engines are preparing to start");
   } else {
      console.log("engines are off");
   }
   ```

3. **Write conditional expressions to satisfy the safety rules.** 

   Use the variables defined from the table above to satisfy the rules listed below.

-  `crewStatus`
   - If the value is `true`, print "Crew Ready"
   - Else print "Crew Not Ready"

   {{% expand "Check Your Solution" %}}
   ```javascript
   if (crewStatus) {
     console.log("Crew Ready");
   } else {
     console.log("Crew Not Ready");
   }
   ```
   {{% /expand %}}

- `computerStatusCode`
   - If the value is `200`, print "Please stand by. Computer is rebooting."
   - Else if the value is `400`, print "Success! Computer online."
   - Else print "ALERT: Computer offline!"

   {{% expand "Check Your Solution" %}}
   ```javascript
   if (computerStatusCode === 200) {
     console.log("Please stand by. Computer is rebooting.");
   } else if (computerStatusCode === 400) {
     console.log("Success! Computer online.");
   } else {
     console.log("ALERT: Computer offline!");
   }
   ```
   {{% /expand %}}

- `shuttleSpeed`
   - If the value is `> 17500`, print "ALERT: Escape velocity reached!"
   - Else if the value is `< 8000`, print "ALERT: Cannot maintain orbit!"
   - Else print "Stable speed"

   {{% expand "Check Your Solution" %}}
   ```javascript
   if (shuttleSpeed > 17500) {
     console.log("ALERT: Escape velocity reached!");
   } else if (shuttleSpeed < 8000) {
     console.log("ALERT: Cannot maintain orbit!");
   } else {
     console.log("Stable speed.");
   }
   ```
   {{% /expand %}}

4. **PREDICT**

   Do these code blocks produce the same result? Answer Yes or No.

   ```javascript
   if (crewStatus && computerStatusCode === 200 && spaceSuitsOn) {
      console.log("all systems go");
   } else {
      console.log("WARNING. Not ready");
   }
   ```

   ```javascript
   if (!crewStatus || computerStatusCode !== 200 || !spaceSuitsOn) {
      console.log("WARNING. Not ready");
   } else {
      console.log("all systems go");
   }
   ```

5. **Monitor the shuttle's fuel status.**

   Implement the checks below using `if` / `else if` / `else` statements. Order is important when working with conditionals, and the checks below are NOT written in the correct sequence. Please read ALL of the checks before coding and then decide on the best order for the conditionals.

- If `fuelLevel` is above 20000 AND `engineTemperature` is at or below 2500, print "Full tank. Engines good."
- If `fuelLevel` is above 10000 AND `engineTemperature` is at or below 2500, print "Fuel level above 50%. Engines good."
- If `fuelLevel` is above 5000 AND `engineTemperature` is at or below 2500, print "Fuel level above 25%. Engines good."
- If `fuelLevel` is at or below 5000 OR `engineTemperature` is above 2500, print "Check fuel level. Engines running hot."
- If `fuelLevel` is below 1000 OR `engineTemperature` is above 3500 OR `engineIndicatorLight` is red blinking, print "ENGINE FAILURE IMMINENT!"
- Otherwise, print "Fuel and engine status pending..."

{{% notice blue "Try It!" "rocket" %}}
Run your code several times ot make sure it prints the correct phrase for each set of conditions.

| **fuelLevel** | **engineTemperature** | **engineIndicatorLight** | **Result**                          |
|---------------|----------------------|--------------------------|-------------------------------------|
| Any           | Any                  | red blinking             | ENGINE FAILURE IMMINENT!            |
| 21000         | 1200                 | NOT red blinking         | Full tank. Engines good.            |
| 900           | Any                  | Any                      | ENGINE FAILURE IMMINENT!            |
| 5000          | 1200                 | NOT red blinking         | Check fuel level. Engines running hot. |
| 12000         | 2600                 | NOT red blinking         | Check fuel level. Engines running hot. |
| 18000         | 2500                 | NOT red blinking         | Fuel level above 50%. Engines good.  |
{{% /notice %}}

{{% expand "Check Your Solution" %}}
```javascript
if (fuelLevel < 1000 || engineTemperature > 3500 || engineIndicatorLight === "red blinking"){
  console.log("ENGINE FAILURE IMMINENT!");
} else if (fuelLevel <= 5000 || engineTemperature > 2500){
  console.log("Check fuel level. Engines running hot.");
} else if (fuelLevel > 20000 && engineTemperature <= 2500){
  console.log("Full tank. Engines good.");
} else if (fuelLevel > 10000 && engineTemperature <= 2500){
  console.log("Fuel level above 50%. Engines good.");
} else if (fuelLevel > 5000 && engineTemperature <= 2500){
  console.log("Fuel level above 25%. Engines good.");
} else {
  console.log("Fuel and engine status pending...");
}
```
{{% /expand %}}

6. **Final bit of fun!**

   The shuttle should only launch if the fuel tank is full and the engine check is OK. *However*, let's establish an override command to ignore any warnings and send the shuttle into space anyway!

- Create the variable `commandOverride`, and set it to be `true` *or*
   `false`.

   If `commandOverride` is `false`, then the shuttle should only launch
   if the fuel and engine check are OK.

   If `commandOverride` is `true`, then the shuttle will launch
   regardless of the fuel and engine status.

- Code the following `if` / `else` check:

   If `fuelLevel` is above 20000 AND `engineIndicatorLight` is NOT
   red blinking OR `commandOverride` is true print "Cleared to
   launch!"

   Else print "Launch scrubbed!"