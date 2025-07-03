# Solar Power Plant Dataset Documentation

## Overview

This dataset contains comprehensive operational data from a solar power plant with detailed measurements from meteorological stations, solar cells, inverters, string monitoring systems, and plant control systems. The dataset spans **17,472 data points** across **109 variables**, providing high-resolution time-series data for solar power generation analysis, predictive modeling, and performance optimization.

⚠️ **Important Note**  
This dataset is proprietary and provided for internal analysis, academic study, or project work. **It must not be shared publicly or redistributed without permission from the data owners.**

## Dataset Structure

- **Total Records**: 17,472  
- **Total Features**: 109  
- **Time Period**: Continuous time-series data  
- **Data Format**: CSV with datetime index  
- **File Size**: ~190MB (estimated)

## Data Categories

### 1. Meteorological Data (`meteorolgicas_`)

Weather and environmental conditions measured at two stations.

#### Irradiance Measurements
- Global Horizontal Irradiance (GHI): `*_ghi`
- Global Inclined Irradiance (GII): `*_gii`
- Rear Irradiance: `*_gii_rear`
- Tracking Deviation: `*_desviacin_incidente`

#### Environmental Conditions
- Ambient Temperature: `*_t_amb`
- Relative Humidity: `*_h_r`
- Wind Speed: `*_ws`
- Wind Direction: `*_wd`
- Datalogger Temperature: `*_t_dlogger`

### 2. Solar Cell Monitoring (`celulas_`)

- Cell Irradiance 1: `*_ir_cel_1`
- Cell Irradiance 2: `*_ir_cel_2`
- Module Temperature: `*_t_mod`
- Ambient Temperature: `*_t_amb`
- Wind Speed: `*_wind_speed`

### 3. String-Level Electrical Data (`inversores_*_strings_`)

- String Voltage: `*_pv_v`
- String Current: `*_pv_i[1-13]`

### 4. Inverter Performance (`inversores_*_inv_`)

- AC Power Output: `*_p`
- DC Power Input: `*_p_dc`
- Total Energy: `*_eact_tot`

### 5. Solar Tracking System (`seguidores_`)

- Position Objective: `*_pos_obj`
- Position Angle: `*_pos_ang`
- Working Mode: `*_workingmode`

### 6. Plant Power Control (`ppc_`)

- Setpoint Power: `ppc_consig_p`
- Total Power: `ppc_p_tot`
- Energy Export: `ppc_eact_export`
- Energy Import: `ppc_eact_imp`

### 7. Theoretical Performance (`ttr_`)

- Theoretical Power: `ttr_potenciaproducible`

## Data Quality and Preprocessing

- High-missing columns (>95% missing): removed  
- Low-missing columns: interpolated + filled  
- Night data (GHI < 5 W/m²): filtered out  
- Outlier detection: validated against physical ranges  

```python
outlier_limits = {
    'irradiance': (0, 1400),
    'temperature': (-10, 80),
    'wind_speed': (0, 40),
    'humidity': (0, 100),
    'power': (0, 48000),
    'string_voltage': (0, 1500),
    'string_current': (0, 40),
}
