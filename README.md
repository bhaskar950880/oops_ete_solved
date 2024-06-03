51. Create a class, Triangle. Its __init__() method should take self, angle1, angle2, and 
angle3 as arguments. Create two objects of Triangle class T1 and T2. For T1 object 
the value of angle1, angle2, and angle3 is 80,30 and 40 respectively. For T2 object 
the value of angle1, angle2, and angle3 is 70,50 and 60 respectively. Create a 
method named check_angles which returns True if the sum of angle1, angle2, and 
angle3 is equal to 180, and False otherwise\



class Triangle:
    def __init__(self, angle1, angle2, angle3):
        self.angle1 = angle1
        self.angle2 = angle2
        self.angle3 = angle3

    def check_angles(self):
        return (self.angle1 + self.angle2 + self.angle3) == 180

# Creating two objects of Triangle class
T1 = Triangle(80, 30, 40)
T2 = Triangle(70, 50, 60)

# Checking if the angles of T1 sum up to 180
print(f"T1 angles sum to 180: {T1.check_angles()}")

# Checking if the angles of T2 sum up to 180
print(f"T2 angles sum to 180: {T2.check_angles()}")



