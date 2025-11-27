**Four-Port Switch Verification Environment (SystemVerilog)**

This project implements a complete SystemVerilog class-based verification environment for a Four-Port Switch design.
It focuses on building packet models, extending them into different packet types, constructing verification components, and integrating them with a SystemVerilog testbench to verify packet routing functionality.

**Project Description**

The switch receives packets on one port and forwards them to one or more output ports depending on the destination encoded in the packet.
This repository contains all the SystemVerilog components required to model, generate, drive, observe, and check these packets.

The work includes:

**Packet Modeling**

A base packet class containing source, target, and payload fields.

Constrained randomization for legal packet generation.

Classification of packets into single-cast, multicast, and broadcast types.

Support functions for printing and identifying packet information.

**Object-Oriented Extensions**

Subclasses for different packet types with their own constraints.

Polymorphic creation of packets using random selection.

Debug support such as tagging and type reporting.

**Verification Component Architecture**

Component base class with naming, hierarchy, and utility functions.

Sequencer for controlled packet generation.

Driver for applying packets to the DUT interface.

Monitor for observing DUT outputs.

Agent bundling sequencer, driver, and monitor.

A top-level verification component integrating all subcomponents.

**Interface Integration**

SystemVerilog interface for switch port signals.

Driver uses the interface to drive packets.

Monitor uses the interface to collect output packets.

**Testbench Integration**

A structured module for instantiating the interface and the verification component.

Configuration of virtual interfaces and port numbers.

Running the verification component to generate and observe traffic.

Support for testing a single port or multiple ports.

**DUT-Level Verification**

A testbench connecting the verification component to all four switch ports.

Monitoring outputs from all ports in parallel.

Checking routing correctness and verifying behavior for different packet types.
