import picamera
import RPi.GPIO as GPIO
from SimpleCV import Image, Barcode


GPIO.setmode(GPIO.BCM)
GPIO.setup(18,GPIO.IN,pull_up_down=GPIO.PUD_UP)


with picamera.PiCamera() as camera:
    camera.start_preview()
    #raw_input()
    a=0
    while a==0:
    	if (GPIO.input(18)==False):
   		camera.capture('/home/pi/QR.png')
    		camera.stop_preview()
       		#GPIO.setup(18, GPIO.OUT, initial=False)
		a=1
   		img = Image('QR.png')
    		barcode=img.findBarcode()
   		info = str(barcode)
		print info[62:]
    
