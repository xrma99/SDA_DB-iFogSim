# SDA_DB-iFogSim

Service Deployment Algorithm based on Data Backup (SDA_DB) is programed by Java and implemented on the *iFogSim*.

The SDA_DB is based on Genetic Algorithm and consists of three new classes.

## VRGameFog

***createFogDevices***: a function used to create physical device environment.

***createApplication***: a function used to create application.

These two methods are what to be modified.

***getfitness***: 
- Call SDA_DB when *flag* is true.
- Return resource cost of each eimulation *flag* is false.

## GAframe: SDA_DB method

Adopt the GA frame. Meanwhile call the getfitness method.

**isValidate**: test if the placement plan is feasible.
- Specific application modules should be placed on mobile FogDevice.
- The FogDevice must have the capacity to process modules placed on it. (test the Mips)

**Hint**:
- Remember to initialize the CloudSim and create application and fogdevices again when testing the placement plan.
- Remember to place the "management" module on *cloud*.

## ModulePlacementMine: int[]-> ModulePlacement
Input the **int[] plan**, return a **ModulePlacement** variable, which is used by *Controller.submitApplication* method.

In addition, this can not only be used as a service deployment algorithm, but also an interface of more service deployment algorithm. Because it can successfully get resource consumption cost of each simulation process via *getfitness* and the result is repeatable as well. The conversion of int[] and ModulePlacement simplifies generation of deployment strategy.
