# Vehicle-Detection-And-Speed-Tracking

### Technologies used :
- Python
- opencv
- dlib

### Tasks breakdown

##### Vehicle Detection
1. We are using Haarcascade classifier to identify vehicles.
  - Vehicle Tracking - ( assigning IDs to vehicles )
2. We have used corelation tracker from dlib library.
3. Speed Calculation
  - We are calculating the distance moved by the tracked vehicle in a second, in terms of pixels, so I need pixel per meter to calculate the distance travelled in meters.With distance travelled per second in meters, I will get the speed of the vehicle.

**How to run project?**
Follow steps:

- Clone repo : git clone `https://github.com/cybersamarth/Detecting-Vehicle-and-speed.git`

- cd (change directory) into vehicle-speed-check `cd vehicle-speed-check`

- Create virtual environment `python -m venv venv`

- Activate virtual environment `./venv/bin/activate`

- Install requirements `pip install -r requirements.txt`

- run speed_check.py script python `speed_check.py`

**Note:**

I have estimated these values manually for the current road to calculate pixels per metre(ppm). Therefore, the value will vary from road to road and have to be adjusted to be used on any other video.

If I talk about the part how i estimated ppm, i need to know the actual width in metres of the road(you can use google to find the approximate width of the road in your country). Also, I have taken the video frame and calculated the width of the road in pixels digitally. Now, I have the width of the road in metres from the real world and in pixels from our video frame. To map the distances betIen these two worlds, I have calculated pixels per metre by dividing distance of road in pixels to metres.

d_pixels gives the pixel distance travelled by the vehicle in one frame of our video processing. To estimate speed in any standard unit first, I need to convert d_pixels to d_metres.

Now, I can calculate the speed(speed = d_meters * fps * 3.6). d_meters is the distance travelled in one frame. We have already calculated the average fps during video processing. So, to get the speed in m/s, just (d_metres * fps) will do. We have multiplied that estimated speed with 3.6 to convert it into km/hr.
