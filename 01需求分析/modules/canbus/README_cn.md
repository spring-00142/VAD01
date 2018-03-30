# Canbus

## 介绍Introduction
  Canbus accepts and executes the control command, and collect chassis status as feedback to control.

## 输入Input
  * Control command

## 输出Output
  * Chassis status
  * Chassis detail status

## 实现工具Implementation
  The major components in canbus module are:
  * CAN client
  * Vehicle including vehicle controller and message manager

  
  Your own CAN client can be implemented in the folder of *can_client* by inheriting from `CanClient` class. Remember to register your CAN client in `CanClientFactory`.

  Your own vehicle controller and message manager can be implemented in the folder of *vehicle* by inheriting from `VehicleController` and `MessageManager`. Remember to register your vehicle in `VehicleFactory`.
