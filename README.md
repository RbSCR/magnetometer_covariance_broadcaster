# magnetometer_covariance_broadcaster

![Project Status](https://img.shields.io/badge/Status-Work%20in%20progress-orange)
![ROS 2](https://img.shields.io/badge/ROS%202-Jazzy%20|%20Kilted%20(Ubuntu%2024.04)-blue?style=flat&logo=ros&logoSize=auto)
![C++](https://img.shields.io/badge/C++-20-blue?style=flat&logo=cplusplus&logoColor=white)
![License](https://img.shields.io/github/license/rbscr/bno08x_rand?label=License)
[![ROS 2 Builder](https://github.com/RbSCR/magnetometer_covariance_broadcaster/actions/workflows/ros2-build.yml/badge.svg)](https://github.com/RbSCR/magnetometer_covariance_broadcaster/actions/workflows/ros2-build.yml)

- [magnetometer\_covariance\_broadcaster](#magnetometer_covariance_broadcaster)
  - [Overview](#overview)
  - [Features](#features)
    - [Parameters](#parameters)
    - [State interfaces](#state-interfaces)
    - [PluginLib library](#pluginlib-library)
    - [Status](#status)

## Overview

Broadcaster to publish readings of a magnetometer with dynamic covariance from the magnetometer.

Can be used with magnetometers like the bno08x.

## Features

- Determines the covariance (matrix diagonal) in the broadcasted magnetic_field message based
  upon the (singular) covariance value in the state interfaces.

### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| sensor_name | string | Defines sensor name used as prefix for its interfaces |
| frame_id | string | Sensor's frame_id in which values are published |

### State interfaces

| Interface | Unit | Notes |
| --------- | ---- | ----- |
| `magnetic_field.x` | Tesla | Magnetic field X |
| `magnetic_field.y` | Tesla | Magnetic field Y |
| `magnetic_field.z` | Tesla | Magnetic field Z |
| `magnetic_field_covariance` | – | Magnetic field covariance |

### PluginLib library

Controller/broadcaster to publish readings of magnetometer with dynamic covariance from the sensor.
Pluginlib-Library: magnetometer_covariance_broadcaster
Plugin: magnetometer_covariance_broadcaster/MagnetometerCovarianceBroadcaster (controller_interface::ControllerInterface)

### Status

- Tested and validated on Raspberry Pi 5 running ROS 2 Kilted/2026-08-21 (Ubuntu 24.04, aarch64)
  using BNO085 hardware.
- Work in progress
