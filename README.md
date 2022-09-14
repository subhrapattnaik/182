# 182
-------------
This faces array has data about the facial features like:
● Positions of eyes,
● Positions of mouth,
● Position of ears,
● How much eye is open,
● Position of left cheek and right cheek,
● How much the person is smiling
--------------
 we are going to use this data to place the filer images over some facial features
 
 Now we will add the glasses (spectacles) filters over the eyes
 
 For this we need "Position of left and right eyes" data from faces array .
 
 
 We would first need to know the face dimensions, like how long and wide the face of the user is.
This can be taken from bounds in the faces array.

Then we can place the glasses filter over the eyes using its position within the face bounds.

For this we will write a function component, Filter1, with a <View> component to render <Image>.

We will pass an object variable, face, as the argument

The values received after calling will be overwritten for faceWidth, faceHeight,leftEyePosition and rightEyePosition.


Now let's have two variables to set the glasses’ image width and height.

const glassWidth;

const glassHeight;

We can set the height of the glasses image as faceHeight/3 to position it over the eyes.

-------------------------------------
filter image should  properly placed over the eyes even when we tilt the face, we are going to set the angle of the glasses image.

For example, if we rotate the head left the filter image must be tilted towards left in the same angle.
For this we can write a function called tranformAngle().


We can use JavaScript atan() method to calculate the angle.

atan() stands for arctangent.Any number passed to atan() method will return an angle value of -PI/2 to +PI/2(i.e. -90° to +90°).
This function will return the angle in radians, that can be converted into degrees using :

Mathematical Formula to convert degrees angle into radian angle:

angleDeg=angleRad*180°/π

For JavaScript we will use: angleDeg=angleRad*180°/PI



Now we can set the style of the <View> and <Image> components. And we have to set the image source.

--------------------------------
Now we can import the Filter1 component in the <Main> component (created in the previous class).
Then we can state to update the values of the component by passing the faces array inside the <Camera> view.

this.state.faces.map....


--------

student can try with Filter2.js
------------
WORKS FINE
--------------

https://snack.expo.dev/@subhra/github.com-whitehatjr-pro-c182-code-ref




 LEFT_EYE,
 RIGHT_EYE


***********************************************************

MAIN.JS


{
                        this.state.faces.map((face, index) => {
                          console.log(face)
                            return <Filter1 key={index} face={face} />
                        })
                    }

