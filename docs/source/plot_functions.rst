Ploting Routines
=============

tiegcmpy provides a range of functions for data visualization. Below are the key plotting routines along with their detailed parameters and usage examples.

Latitude vs Longitude Contour Plots
-----------------------------------

This function generates a contour plot of a variable against latitude and longitude.

.. function:: plt_lat_lon(datasets, variable_name, time=None, mtime=None, level=None, variable_unit=None, contour_intervals=None, contour_value=None, coastlines=False, latitude_minimum=None, latitude_maximum=None, longitude_minimum=None, longitude_maximum=None, localtime_minimum=None, localtime_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset/s using xarray.
    - variable_name (str): The name of the variable with latitude, longitude, ilev dimensions.
    - time (np.datetime64, optional): The selected time, e.g., '2022-01-01T12:00:00'.
    - mtime (array, optional): The selected time as a list, e.g., [1, 12, 0] for 1st day, 12 hours, 0 mins.
    - level (float, optional): The selected lev/ilev value.
    - variable_unit (str, optional): The desired unit of the variable.
    - contour_intervals (int, optional): The number of contour intervals. Defaults to 20.
    - contour_value (int, optional): The value between each contour interval.
    - coastlines (bool, optional): Shows coastlines on the plot. Defaults to False.
    - latitude_minimum (float, optional): Minimum latitude to slice plots. Defaults to -87.5.
    - latitude_maximum (float, optional): Maximum latitude to slice plots. Defaults to 87.5.
    - longitude_minimum (float, optional): Minimum longitude to slice plots. Defaults to -180.
    - longitude_maximum (float, optional): Maximum longitude to slice plots. Defaults to 175.
    - localtime_minimum (float, optional): Minimum localtime to slice plots.
    - localtime_maximum (float, optional): Maximum localtime to slice plots.

Example:
    Load datasets and generate a Latitude vs Longitude contour plot.

    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        value_of_mtime = [360, 0, 0, 0]
        pressure_level = 4.0
        unit_of_variable = 'K'
        intervals = 20
        plot = ty.plt_lat_lon(datasets, variable_name, mtime=value_of_mtime, level=pressure_level, variable_unit=unit_of_variable, contour_intervals=intervals)

Pressure Level vs Variable Line Plot
------------------------------------

This function generates a line plot of a variable at a specific latitude and optional longitude, time, and local time.

.. function:: plt_lev_var(datasets, variable_name, latitude, time=None, mtime=None, longitude=None, localtime=None, variable_unit=None, level_minimum=None, level_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset/s using xarray.
    - variable_name (str): The name of the variable with latitude, longitude, ilev dimensions.
    - latitude (float): The specific latitude value for the plot.
    - time (np.datetime64, optional): The selected time, e.g., '2022-01-01T12:00:00'.
    - mtime (array, optional): The selected time as a list, e.g., [1, 12, 0] for the 1st day, 12 hours, 0 mins.
    - longitude (float, optional): The specific longitude value for the plot.
    - localtime (float, optional): The specific local time value for the plot.
    - variable_unit (str, optional): The desired unit of the variable.
    - level_minimum (float, optional): Minimum level value for the plot. Defaults to -8.
    - level_maximum (float, optional): Maximum level value for the plot. Defaults to 8.

Example:
    Load datasets and generate a Pressure Level vs Variable Line plot.

    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        latitude = 30.0
        time_value = '2022-01-01T12:00:00'
        longitude_value = 45.0
        unit_of_variable = 'K'
        plot = ty.plt_lev_var(datasets, variable_name, latitude, time=time_value, longitude=longitude_value, variable_unit=unit_of_variable)

# Extracting the details for "Pressure level vs Longitude Contour Plot" and "Pressure Level vs Latitude Contour Plot" 
# from the README.md to create corresponding sections in functionality.rst

Pressure level vs Longitude Contour Plot
----------------------------------------

This function generates a contour plot of a variable at a specific latitude against longitude, with optional time and local time.

.. function:: plt_lev_lon(datasets, variable_name, latitude, time=None, mtime=None, variable_unit=None, contour_intervals=20, contour_value=None, level_minimum=None, level_maximum=None, longitude_minimum=None, longitude_maximum=None, localtime_minimum=None, localtime_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset(s) using xarray.
    - variable_name (str): The name of the variable with latitude, longitude, and ilev dimensions.
    - latitude (float): The specific latitude value for the plot.
    - time (np.datetime64, optional): The selected time, e.g., '2022-01-01T12:00:00'.
    - mtime (array, optional): The selected time as a list, e.g., [1, 12, 0] for the 1st day, 12 hours, 0 minutes.
    - variable_unit (str, optional): The desired unit of the variable.
    - contour_intervals (int, optional): The number of contour intervals. Defaults to 20.
    - contour_value (int, optional): The value between each contour interval.
    - level_minimum (float, optional): Minimum level value for the plot. Defaults to -6.75.
    - level_maximum (float, optional): Maximum level value for the plot. Defaults to 6.75.
    - longitude_minimum (float, optional): Minimum longitude value for the plot. Defaults to -180.
    - longitude_maximum (float, optional): Maximum longitude value for the plot. Defaults to 175.
    - localtime_minimum (float, optional): Minimum localtime value for the plot.
    - localtime_maximum (float, optional): Maximum localtime value for the plot.

Example:
    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        latitude = 30.0
        time_value = '2022-01-01T12:00:00'
        unit_of_variable = 'K'
        contour_intervals = 20
        plot = ty.plt_lev_lon(datasets, variable_name, latitude, time=time_value, variable_unit=unit_of_variable, contour_intervals=contour_intervals)

Pressure Level vs Latitude Contour Plot
---------------------------------------

This function generates a contour plot of a variable against pressure level and latitude.

.. function:: plt_lev_lat(datasets, variable_name, longitude, time=None, mtime=None, localtime=None, variable_unit=None, contour_intervals=None, contour_value=None, coastlines=False, level_minimum=None, level_maximum=None, latitude_minimum=None, latitude_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset/s using xarray.
    - variable_name (str): The name of the variable with lev/ilev, lat dimensions.
    - longitude (float): The specific longitude value for the plot.
    - time (np.datetime64, optional): The selected time, e.g., '2022-01-01T12:00:00'.
    - mtime (array, optional): The selected time as a list, e.g., [1, 12, 0] for the 1st day, 12 hours, 0 mins.
    - localtime (float, optional): The specific local time value for the plot.
    - variable_unit (str, optional): The desired unit of the variable.
    - contour_intervals (int, optional): The number of contour intervals. Defaults to 20.
    - contour_value (int, optional): The value between each contour interval.
    - coastlines (bool, optional): Shows coastlines on the plot. Defaults to False.
    - level_minimum (float, optional): Minimum level value for the plot.
    - level_maximum (float, optional): Maximum level value for the plot.
    - latitude_minimum (float, optional): Minimum latitude to slice plots.
    - latitude_maximum (float, optional): Maximum latitude to slice plots.

Example:
    Load datasets and generate a Pressure Level vs Latitude contour plot.

    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        longitude_value = 45.0
        time_value = '2022-01-01T12:00:00'
        unit_of_variable = 'K'
        plot = ty.plt_lev_lat(datasets, variable_name, longitude=longitude_value, time=time_value, variable_unit=unit_of_variable)

Pressure Level vs Time Contour Plot
-----------------------------------

This function creates a contour plot of a variable against pressure level and time.

.. function:: plt_lev_time(datasets, variable_name, latitude, longitude=None, localtime=None, variable_unit=None, contour_intervals=None, contour_value=None, coastlines=False, level_minimum=None, level_maximum=None, time_minimum=None, time_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset/s using xarray.
    - variable_name (str): The name of the variable with lev/ilev, time dimensions.
    - latitude (float): The specific latitude value for the plot.
    - longitude (float, optional): The specific longitude value for the plot.
    - localtime (float, optional): The specific local time value for the plot.
    - variable_unit (str, optional): The desired unit of the variable.
    - contour_intervals (int, optional): The number of contour intervals. Defaults to 20.
    - contour_value (int, optional): The value between each contour interval.
    - coastlines (bool, optional): Shows coastlines on the plot. Defaults to False.
    - level_minimum (float, optional): Minimum level value for the plot.
    - level_maximum (float, optional): Maximum level value for the plot.
    - time_minimum (np.datetime64, optional): Minimum time for the plot.
    - time_maximum (np.datetime64, optional): Maximum time for the plot.

Example:
    Load datasets and generate a Pressure Level vs Time contour plot.

    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        latitude_value = 30.0
        time_min = '2022-01-01T00:00:00'
        time_max = '2022-01-02T00:00:00'
        unit_of_variable = 'K'
        plot = ty.plt_lev_time(datasets, variable_name, latitude=latitude_value, time_minimum=time_min, time_maximum=time_max, variable_unit=unit_of_variable)

Latitude vs Time Contour Plot
-----------------------------

This function creates a contour plot of a variable against latitude and time.

.. function:: plt_lat_time(datasets, variable_name, level, longitude=None, localtime=None, variable_unit=None, contour_intervals=None, contour_value=None, coastlines=False, latitude_minimum=None, latitude_maximum=None, time_minimum=None, time_maximum=None)

Parameters:
    - datasets (xarray): The loaded dataset/s using xarray.
    - variable_name (str): The name of the variable with lat, time dimensions.
    - level (float): The specific pressure level for the plot.
    - longitude (float, optional): The specific longitude value for the plot.
    - localtime (float, optional): The specific local time value for the plot.
    - variable_unit (str, optional): The desired unit of the variable.
    - contour_intervals (int, optional): The number of contour intervals. Defaults to 20.
    - contour_value (int, optional): The value between each contour interval.
    - coastlines (bool, optional): Shows coastlines on the plot. Defaults to False.
    - latitude_minimum (float, optional): Minimum latitude to slice plots.
    - latitude_maximum (float, optional): Maximum latitude to slice plots.
    - time_minimum (np.datetime64, optional): Minimum time for the plot.
    - time_maximum (np.datetime64, optional): Maximum time for the plot.

Example:
    Load datasets and generate a Latitude vs Time contour plot.

    .. code-block:: python

        datasets = ty.load_datasets(directory, dataset_filter)
        variable_name = 'TN'
        pressure_level = 4.0
        time_min = '2022-01-01T00:00:00'
        time_max = '2022-01-02T00:00:00'
        unit_of_variable = 'K'
        plot = ty.plt_lat_time(datasets, variable_name, level=pressure_level, time_minimum=time_min, time_maximum=time_max, variable_unit=unit_of_variable)
