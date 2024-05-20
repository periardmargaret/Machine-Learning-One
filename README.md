#include <iostream>
#include <iomanip> // For setprecision

using namespace std;

// Constants for unit conversions
const double INCHES_PER_FOOT = 12.0;
const double FEET_PER_MILE = 5280.0;
const double MINUTES_PER_HOUR = 60.0;
const double MOWER_WIDTH_INCHES = 18.0;

int main() {
    // Declare variables to hold the input values
    double lawnLength, lawnWidth, houseLength, houseWidth, walkingSpeed;

    // Prompt the user for input
    cout << "Mowing the lawn by [Your Name]\n" << endl;
    cout << "Enter five numbers separated by blanks" << endl;
    cout << "They represent the length and width of lawn in feet," << endl;
    cout << "the length and width of the house in feet" << endl;
    cout << "and the walking speed in mph" << endl;

    // Read input values
    cin >> lawnLength >> lawnWidth >> houseLength >> houseWidth >> walkingSpeed;

    // Echo the input
    cout << "\nThe lawn is " << lawnLength << " by " << lawnWidth << " feet" << endl;
    cout << "The house is " << houseLength << " by " << houseWidth << " feet" << endl;
    cout << "Your walking speed is " << walkingSpeed << " mph\n" << endl;

    // Calculate areas
    double lawnArea = lawnLength * lawnWidth;
    double houseArea = houseLength * houseWidth;
    double areaToMow = lawnArea - houseArea;

    // Print the area to mow
    cout << "The area to mow is " << areaToMow << " square feet\n";

    // Calculate mowing rate in square feet per minute
    double mowerWidthFeet = MOWER_WIDTH_INCHES / INCHES_PER_FOOT;
    double walkingSpeedFeetPerMinute = (walkingSpeed * FEET_PER_MILE) / MINUTES_PER_HOUR;
    double mowingRate = walkingSpeedFeetPerMinute * mowerWidthFeet;

    // Print the mowing rate
    cout << "You can mow " << fixed << setprecision(1) << mowingRate << " sq. ft. per min\n";

    // Calculate time to mow the lawn
    double timeToMow = areaToMow / mowingRate;

    // Print the time to mow
    cout << "Time to mow the lawn is " << fixed << setprecision(4) << timeToMow << " minutes\n";

    return 0;
}
