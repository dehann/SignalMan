=========
SignalMan
=========

Introduction
------------

Useful signal manipulation functions. Current class definitions include:

    class DataFileLogger
    class SchmittTrigger
    class BipolarSchmittTrigger
    class NumericalDiff
    class DistributedDiff
    class MidpointInt
    class RateChange
    class MedianFilter
    class BlipFilter
    class CumulativeAverage
    class ExpireTimer
    class Gaussian

Doesn't yet have a stand alone test application -- work in progress.

Dependencies
------------

This library depends on the following packages:

    cmake
    boost
    Eigen

To download and compile
-----------------------

Get dependencies:

    sudo apt-get install libboost-dev cmake libeigen3-dev

Get SignalMan:

    git clone https://github.com/dehann/SignalMan.git

Navigate to the build directory:

    cd SignalMan/build
    cmake ..
    make -j







