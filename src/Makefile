# ls | sed 's/\.c/\.o /' | tr -d '\n'
CHIPMUNK_OBJ = chipmunk.o cpArbiter.o cpArray.o cpBBTree.o cpBody.o cpCollision.o cpConstraint.o cpDampedRotarySpring.o cpDampedSpring.o cpGearJoint.o cpGrooveJoint.o cpHashSet.o cpHastySpace.o cpMarch.o cpPinJoint.o cpPivotJoint.o cpPolyline.o cpPolyShape.o cpRatchetJoint.o cpRobust.o cpRotaryLimitJoint.o cpShape.o cpSimpleMotor.o cpSlideJoint.o cpSpace.o cpSpaceComponent.o cpSpaceDebug.o cpSpaceHash.o cpSpaceQuery.o cpSpaceStep.o cpSpatialIndex.o cpSweep1D.o 

CFLAGS = -g3 -Wall -Wextra -Wshadow -Wvla -fPIC -pedantic -I../include/

default: chipmunk_static.a chipmunk.so

chipmunk_static.a: $(CHIPMUNK_OBJ)
	$(AR) rcs $@ $(CHIPMUNK_OBJ)
	
chipmunk.so: $(CHIPMUNK_OBJ)
	$(CC) -shared -o $@ $(CHIPMUNK_OBJ)

%.o: %.c
	$(CC) -c -o $@ $< $(CFLAGS)

.PHONY: clean
clean:
	$(RM) $(CHIPMUNK_OBJ) chipmunk_static.a chipmunk_dynamic.so
