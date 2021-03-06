

All the datasets are stored in the [POLY](http://tetgen.berlios.de/fformats.poly.html) format: 


# cube
  * unit cube with 6 faces
  * valid

# cube2
  * unit cube with a hole in top face located outside
  * invalid (in 2D the top face is not acc. to SFS)

# cube3
  * unit cube with a hole (inner ring) in the top face
  * invalid (the inner ring isn't filled by another face, so not watertight)

# cube4
  * unit cube with one extra face inside another face
  * invalid 

# cube5
  * cube3 where there are extra faces that fill the hole on top face
  * valid

# cube6
  * cube5 where hole (inner ring) is touching the outer ring of a face
  * valid

# cube8
  * unit cube with an extra vertex on an edge. Only one of the 2 incident faces has
it explicitly. 
  * invalid (geometrically valid, but topologically invalid. Thus: invalid) 
  * note: Oracle Spatial reports valid 

# cube9
  * unit cube with one face (face #0) with opposite orientation
  * invalid

# cube10
  * unit cube with one face missing (bottom one)
  * invalid

# cube11
  * unit cube with one extra face in the middle, splitting the cube in two parts
  * invalid

# cube12
  * unit cube with one dangling face touching the cube at one point only; the dangling face is the last in the list
  * invalid

# cube13
  * unit cube with top face not planar
  * invalid

# cube14
  * axis-aligned cube with normals all pointing inwards
  * invalid
  
# cube14r
  * axis-unaligned cube with normals all pointing inwards; 
  * invalid
 
# cube14r2
  * axis-unaligned cube with normals all pointing outwards; the first extreme point along x has a flat star
  * valid
# cube15
  * cube with one dangling face, touching only at one point; the dangling face is the 1st in the list
  * invalid

# cube16
  * cube with one extra face "floating" in the air, not touching
  * invalid

# cube17
  * cube3 where inner ring is collapsed to a line
  * invalid

# cube18
  * cube1 where top face has a bow tie orientation 
  * invalid

# cube19
  * unit cube with a hole (inner ring) in the top face having same orientation as outer ring
  * invalid

# cube20
  * flat cube, ie with volume of 0
  * invalid

# cube21
  * 2 unit cubes not touching at all, one above the other separated by 1unit
  * invalid

# concave
  * concave shape; top and bottom faces are concave polygons
  * valid

# torus
  * a "squared donut", genus of the shell is 1
  * valid

# torus2
  * torus where the hole in the top/bottom faces touches the side surfaces
  * invalid

# house
  * cube with a pyramidal roof
  * valid

# house2
  * house with tip below the ground
  * invalid

# house3
  * house with tip touching the bottom faces
  * invalid

# house4
  * house with a flat roof (4 triangular faces)
  * valid

# py1
  * invalid as outer shell (all normals pointing inwards)
  * a pyramid used as inner shell for cube
  * cube + py1 = valid

# py2
  * invalid as outer shell (all normals pointing inwards)
  * pyramid touching top face one point. 
  * cube + py2 = valid
  * (Oracle is wrong on that one: oracle=54513)

# py3
  * invalid as outer shell (all normals pointing inwards)
  * pyramid intersecting the cube (tip goes through the top face)
  * cube + py3 = invalid
  * (Oracle agrees: oracle=54512)

# py4
  * invalid as outer shell (all normals pointing inwards)
  * bottom face is shared with bottom face of the cube
  * cube + py4 = invalid

# py5
  * invalid as outer shell (all normals pointing inwards)
  * touching py1 at one point
  * cube + py1 + py5 = valid

# py6
  * invalid as outer shell (all normals pointing inwards)
  * touching py1 along an edge
  * cube + py1 + py6 = valid

# py7 
  * invalid as outer shell (all normals pointing inwards)
  * sharing a face with py1 (face connected)
  * cube + py1 + py7 = invalid (2 holes face touching)

# py8
  * invalid as outer shell (all normals pointing inwards)
  * sharing *partly* a face with py1 
  * cube + py1 + py8 = invalid (2 holes face touching)

# py9
  * invalid as outer shell (all normals pointing inwards)
  * pyramid complete outside the outer shell of cube
  * cube + py9 = invalid

# py10
  * invalid as outer shell (all normals pointing inwards)
  * pyramid outside the outer shell of cube, but face adjacent
  * cube + py10 = invalid

# py11
  * invalid as outer shell (all normals pointing inwards)
  * pyramid encloses the whole cube
  * cube + py11 = invalid

# blocker1
  * invalid as outer shell (all normals pointing inwards)
  * kinda pyramid that splits the interior of cube into 2 non-connected parts
  * cube + blocker1 = invalid

