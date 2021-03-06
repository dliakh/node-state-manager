# GENIVI Node State Manager (NSM) README
This is the official source code repository of the GENIVI Node State Manager. 

## About
The Node State Manager (NSM) is the central functional component that gathers information on the current running state of the embedded system. The NSM component provides a common implementation framework for the system state machine. It collates information from multiple sources and uses the data to determine the current state(s). Based on the given data, the NSM notifies registered consumers (applications or other platform components) of relevant changes in system state. Node state information can also be requested on-demand via provided D-Bus interfaces. The node state manager also provides shutdown management including shutdown request notification to consumers. The node state management is the last/highest level of escalation on the node and will issue the reset instruction and supply control logic. It is notified of errors and other status signals from components that are responsible for monitoring system health.

Internally, node state management is made up of a common generic component, Node State Manager (NSM), and a system-specific state machine (NSMC) that is plugged into the Node State Manager. Through this architecture there can be a standardized solution with stable interfaces towards the applications, which still allows for product-specific behavior through the definition of the specific state machine.

More information on the software can be found here: https://at.projects.genivi.org/wiki/display/PROJ/Node+State+Manager

## License
This software is licensed under the MPL 2.0
For licensing information see the COPYING file, 
distributed along with this project.

## Build Dependencies and Instructions
The NodeStateManager needs glib >= 2.30.0 to be compiled.
In addition, the NodeStateManager(NSM) has dependencies
to the NodeStateMachine (NSMC) and NodeStateAccess (NSMA).

The NSMC is delivered within this package as a stub.
To understand the task it performs, please see its interface header.

Please note: Due to legal restrictions the NSMA currently
is being built as a shared library that is used by the NSM.
