# Project 2: Transformations

1. Create a private git repository on Bitbucket containing all of the files in transformations.zip, and share it with dhunter68 with admin access.  The name of this repository should contain the string "Project2".

2. The skeleton code should compile and produce an executable called "trans".  It shows one cube that can be manipulated with the mouse.  The position of the cube is determined by the global matrix g_objectRbt[0]. Move the first cube a little to the left and add a second cube (and give it its own matrix) to the right.  Make sure both cubes appear in the window initially and the two cubes do not overlap. Give the two cubes different colors and different textures.

3. Originally, the scene is viewed looking down the negative z-axis of the sky frame. Make it so that pressing the "v" key cycles the viewpoint between three frames: (1) the sky frame, (2) the frame of cube 1, (3) the frame of cube 2. 

4. In order to do part 5 below, you must first implement the transFact and linFact functions in matrix4.h.  These are described on page 45 of [G].

5. Originally, only cube 1 can be manipulated, and there is something wrong with the way the motions correspond to mouse movements.  Make it so that pressing the "o" key cycles through three different objects to manipulate: (1) cube 1, (2) cube 2, (3) the sky camera. Furthermore, the frame with respect to which each object is manipulated should be set so that the mouse motions always move the objects the right way:
   *   If the object being manipulated is a cube and the current eye is the sky camera, then the frame should be the cube-sky frame: its center should coincide with the cube's center, and its axes should be parallel to the sky frame's axes.
   *  If the object being manipulated is cube i and the current eye is cube j, then the frame should be the cube i - cube j frame: its center should coincide with cube i's center, and its axes should be parallel to cube j's axes.
   *  If the object being modified is the sky camera and the eye is the sky camera, there are two choices; pressing the "m" key should toggle between them: (1) the world-sky frame (center at world frame, axes parallel to sky frame), and (2) the sky-sky frame, i.e. the sky camera's frame.
   * Don't allow the sky camera to be manipulated when the current view is a cube view.

6. Add some feature to the cubes (e.g., faces, noses) so you can tell which direction they are looking.
