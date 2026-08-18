# SolidWorks Study Notes

> Current learning progress: 17 / 43
>
> These notes are updated according to actual learning progress. Each lesson contains only: Core Summary, Common Mistakes, and Operation Notes.

<!-- video-course-notes-progress: P17/43 -->

# Phase 1: Interface and Sketching Fundamentals (P01–P08)

## P01 Lesson 1: Course Introduction, Software Interface, and Basic Operations

### Core Summary

- SOLIDWORKS primarily uses three document types: parts, assemblies, and drawings. Each document type displays its own tools and FeatureManager design tree content.
- The basic part-modeling workflow is: select a plane → create a sketch → apply dimensional constraints → create a feature.
- The FeatureManager design tree records every modeling step. Rotating the view or using Normal To changes only the viewing direction, not the model itself.

### Common Mistakes

- Failing to save immediately after creating a part, or neglecting to save periodically while modeling;
- Starting a sketch without first selecting a reference plane;
- Assuming a blue rectangle is already fully defined;
- Mistaking view rotation for a change to the model's actual orientation;
- Failing to expand an extrude feature and therefore being unable to find its sketch.

### Operation Notes

- Ctrl+N creates a new document; Ctrl+S saves the current document.
- Sketch > Sketch > Front Plane creates a sketch on the Front Plane.
- Sketch > Center Rectangle, draw from the origin and dimension both sides to 100 mm to create a fully defined square.
- Features > Extruded Boss/Base > Depth 100 mm creates a 100 mm cube.
- Hold and drag the middle mouse button to rotate the model freely.
- View Orientation > Normal To aligns the view perpendicular to the selected plane.

---

## P02 Study Guide and Learning Roadmap

### Core Summary

- Keep SOLIDWORKS open while watching the lessons and perform each operation yourself instead of only watching.
- The learning sequence is divided into sketching, parts, assemblies, and drawings, with exercises accompanying every stage.
- After learning the basic functions, continue with complete projects. True mastery means being able to complete a design independently.

### Common Mistakes

- Watching videos or copying steps without practicing simultaneously in the software;
- Watching lessons continuously while skipping the stage exercises in the learning roadmap;
- Giving up when an exercise becomes difficult instead of reviewing the relevant lesson and solution;
- Treating “understood it” as “mastered it” without rebuilding the model from memory.

### Operation Notes

- This lesson introduces no new software operations.

---

## P03 Lesson 2: Sketching

### Core Summary

- Common sketch tools include Line, Rectangle, Circle, Arc, Slot, Sketch Fillet, Sketch Chamfer, and Point. Their drawing methods can be inferred from the icons and on-screen prompts.
- A sketch is usually drawn approximately first, then its position and size are defined with geometric relations and Smart Dimensions.
- Blue sketch entities still have degrees of freedom; black entities are fully defined. Conflicting geometric relations cause errors.
- Circle centers, line endpoints, and rectangle corners are all points. Standalone points can also locate pattern centers and other geometry.

### Common Mistakes

- Applying conflicting relations, such as Horizontal and Vertical, to the same line;
- Clicking the exit command after drawing and unintentionally discarding the current sketch edit;
- Dimensioning only the contour size without locating the contour relative to the origin;
- Confusing a slot's centerline length with its width;
- Ignoring the horizontal, vertical, and tangent indicators beside the pointer and creating incorrect relations.

### Operation Notes

- Ctrl+Z undoes the previous operation.
- Sketch confirmation corner > green check mark saves the sketch and exits sketch editing.
- FeatureManager design tree > Sketch > right-click > Edit Sketch reopens an existing sketch.
- Hold the right mouse button and gesture upward to start Smart Dimension quickly.
- Ctrl+middle-mouse drag pans the sketch view.
- Sketch > Sketch Fillet, select a corner and enter a radius to replace the two edges with a tangent arc.

![Lesson 2: Common sketch entities and dimensions](./images/P03-sketch-tools-examples.png)

---

## P04 Lesson 3: Sketch Relations and Editing

### Core Summary

- After selecting multiple sketch entities, you can add relations such as Perpendicular, Parallel, Equal, Collinear, Tangent, and Symmetric.
- Power Trim removes extra segments continuously as you drag across them; holding Shift while dragging can extend entities.
- Convert Entities projects existing model edges or sketches into the active sketch.
- Offset Entities creates an offset contour from model edges or sketch entities with a specified distance, direction, or bidirectional offset.

### Common Mistakes

- Failing to hold Ctrl and select every required entity, causing a relation to be unavailable or applied to the wrong entities;
- Adding duplicate dimensions and geometric relations, which overdefines the sketch;
- Dragging Power Trim across a segment that should remain;
- Ignoring the association between converted entities and their source edges or sketches;
- Failing to confirm that sketch editing is still active, causing later commands to affect the wrong objects.

### Operation Notes

- Hold Ctrl and select multiple sketch entities to apply a common geometric relation.
- Sketch > Trim Entities > Power Trim, hold the left mouse button and drag across segments to trim continuously.
- While Power Trim is active, hold Shift and drag an entity to extend it.
- Sketch > Convert Entities projects existing edges or sketches into the current sketch.
- Sketch > Offset Entities sets the offset distance, direction, or bidirectional offset.
- Smart Dimension, select two lines in sequence to dimension the angle between them.

![Lesson 3: Convert Entities example](./images/P04-convert-entities-example.png)

---

## P05 Supplementary Lesson 1: Invalid Default Templates and Convert Entities

### Core Summary

- An “invalid default template” message usually means that the part or assembly template path in System Options does not point to an existing template file.
- Document Properties control drafting standards, dimension fonts, and similar settings. To apply changes to new documents, save the document as a template and assign it as the default template.
- Convert Entities extracts contours from model faces, edges, or existing sketches, reducing repeated drawing and inconsistent dimensions.

### Common Mistakes

- Dismissing the invalid-default-template message without repairing the template path;
- Closing the file after changing the dimension font without saving it as a template;
- Confusing part templates (`*.prtdot`) with assembly templates (`*.asmdot`);
- Replacing only the part template and forgetting to configure the assembly template separately;
- Running Convert Entities before entering the target sketch or selecting the wrong face.

### Operation Notes

- System Options > Default Templates, reselect valid part and assembly templates to resolve an invalid-default-template error.
- Document Properties > Dimensions > Font > Height 5.5 mm enlarges dimension text.
- File > Save As > Part Template (`*.prtdot`) saves the modified part template.
- File > Save As > Assembly Template (`*.asmdot`) saves the modified assembly template.
- Sketch > Convert Entities > select a model face to extract its boundary contour. Enter the sketch first, then select the face.

![Supplementary Lesson 1: Convert Entities from a face](./images/P05-convert-entities-face-example.png)

---

## P06 Supplementary Lesson 2: Sketching Workflow

### Core Summary

- Draw the complete contour first and check automatically created relations, then use Smart Dimensions to fully define the sketch step by step.
- Entering a line length directly in the PropertyManager does not replace a Smart Dimension. Driving dimensions and geometric relations are what actually control the sketch.
- A fully defined sketch requires both shape and size constraints, plus overall location through the origin, reference geometry, or locating dimensions.
- When a sketch remains blue, drag its entities to observe the remaining degrees of freedom and identify missing constraints from the movement direction.

### Common Mistakes

- Assuming that a line is constrained after entering its length in the Line PropertyManager;
- Dimensioning every size but failing to locate the sketch relative to the origin;
- Converting a driven dimension back to driving and creating duplicate dimensions or an overdefined sketch;
- Accepting unrelated automatic relations such as Vertical or Tangent;
- Deleting many correct relations after an error instead of first dragging the sketch to inspect its degrees of freedom.

### Operation Notes

- Smart Dimension > select a line to create a driving length dimension.
- Status bar > Units > MMGS changes the current part's length unit to millimeters.
- Dimension PropertyManager > Other > Driven switches between driving and driven dimensions.
- Hold Ctrl, select a sketch entity and the origin, then add Coincident to locate the sketch at the origin.
- Drag a blue sketch entity to determine which direction still lacks a constraint.

![Supplementary Lesson 2: Driving and driven dimensions](./images/P06-driving-dimensions-example.png)

---

## P07 Lesson 4: Sketch Mirroring, Patterns, and Advanced Drawing Practice

### Core Summary

- Mirror Entities requires separate selections for the entities to mirror and the mirror axis; the mirror axis must be a line.
- Linear Sketch Pattern can define the instance count, spacing, and angle in two directions. The instance count includes the original entity.
- Circular Sketch Pattern requires a center point, patterned entities, instance count, and angle, and also supports equal spacing and skipped instances.
- Break complex sketches into local sections and complete each section through the cycle: draw → add relations → add dimensions → fully define.

### Common Mistakes

- Failing to activate the Mirror About selection box and accidentally adding the axis to Entities to Mirror;
- Assuming the pattern count excludes the original entity and creating one extra instance;
- Selecting the wrong center for a circular pattern;
- Drawing an entire complex sketch at once, making underdefined or conflicting areas difficult to locate;
- Confusing horizontal distance, vertical distance, and a line's true length.

### Operation Notes

- Sketch > Mirror Entities, select Entities to Mirror first, then activate Mirror About and select a line.
- Linear Sketch Pattern > Number of Instances includes the original entity.
- Linear Sketch Pattern > Direction 1/Direction 2 separately controls count, spacing, and direction angle.
- Circular Sketch Pattern > Pattern Center accepts a circle center or a standalone sketch point.
- Circular Sketch Pattern > Instances to Skip removes selected pattern positions.

![Lesson 4: Mirror and sketch pattern exercise](./images/P07-mirror-array-sketch-example.png)

---

## P08 Exercise Overview

### Core Summary

- Reinforce lessons promptly with sketch, part, assembly, and drawing exercises; otherwise the operations will be forgotten quickly.
- Match exercises to the learning stage: complete exercises for one function group immediately before moving to the next stage.
- Assembly exercises teach how to combine existing parts, while complete projects teach how to design parts from scratch and assemble them. Neither replaces the other.

### Common Mistakes

- Waiting too long after a lesson to practice and discovering later that the operations have been forgotten;
- Skipping supplementary lessons or changing the course order and attempting exercises beyond the current stage;
- Looking at the solution immediately after encountering difficulty instead of first trying independently;
- Completing only assembly exercises with ready-made parts and never completing a design-from-scratch project;
- Postponing every exercise until the entire course has been watched.

### Operation Notes

- This lesson introduces no new software operations.

---

# Phase 2: Part Features and Model Modification (P09–P20)

## P09 Supplementary Lesson 3: Feature Preview

### Core Summary

- Extruded Boss/Base fundamentally defines where the extrusion starts and where it ends, then turns a 2D contour into a solid along a specified direction.
- The extrusion can start on the sketch plane or at an offset from the sketch plane.
- End conditions include Blind, two directions, Mid Plane, Up to Surface, and Offset from Surface.
- Controlling an end condition with a model face expresses the geometric relationship more robustly than manually calculating a fixed depth.

### Common Mistakes

- Confusing the start condition with the end condition and changing the distance in the wrong option;
- Changing an offset value without checking Reverse Direction, causing the solid to appear on the wrong side of the sketch;
- Entering separate values for Direction 1 and Direction 2 when an equal two-sided extrusion should use Mid Plane;
- Forcing alignment to an existing face with a fixed depth, causing the model to lose alignment after later changes;
- Using Offset from Surface without confirming the offset direction.

### Operation Notes

- Extruded Boss/Base > Direction 1 > Reverse Direction switches the extrusion direction.
- Extruded Boss/Base > Direction 2 (selected) extrudes separately in both directions from the sketch.
- Extruded Boss/Base > End Condition > Mid Plane extrudes equal distances on both sides of the sketch.
- Extruded Boss/Base > Start Condition > Offset begins the extrusion at a specified distance from the sketch plane.
- Extruded Boss/Base > End Condition > Up to Surface ends the extrusion at the selected model face.

---

## P10 Lesson 5: Feature Creation and the FeatureManager Design Tree

### Core Summary

- Boss features add material and cut features remove material. Extrude, Revolve, Sweep, and Loft create geometry in different ways.
- Extruded Boss/Base requires a start condition, direction, and end condition; existing vertices, faces, or bodies can control the endpoint.
- Thin Feature extrudes the edges of a closed contour into walls with thickness and can control thickness direction, mid-plane thickness, or two-direction thickness.
- The FeatureManager design tree records modeling order. Editing an upstream sketch or feature updates downstream features that reference it.

### Common Mistakes

- Creating a practice file without saving it first;
- Setting an offset start or termination face without checking Reverse Direction;
- Confusing Up to Surface, Up to Body, and Offset from Surface;
- Reversing Thin Feature thickness so the model grows outside the intended contour;
- Editing an upstream sketch without considering references used by downstream features.

### Operation Notes

- Extruded Boss/Base > Start Condition > Offset changes the extrusion's start position.
- Extruded Boss/Base > End Condition can use Next, Up to Vertex, Up to Surface, Up to Body, or Mid Plane.
- Extruded Boss/Base > Thin Feature controls wall thickness, direction, Mid Plane, or two-direction thickness.
- Press F to fit the model to the graphics area.
- FeatureManager design tree > feature > Edit Feature reopens the feature parameters.
- FeatureManager design tree > expand feature > sketch > Edit Sketch modifies the source sketch used by the feature.

![Lesson 5: Thin Feature result](./images/P10-thin-feature-result.png)

---

## P11 Lesson 6: Feature Creation, Part 2

### Core Summary

- Cut-Extrude supports end conditions such as Blind, Through All, and Up to Surface. Both model faces and reference planes can serve as termination surfaces.
- Reference planes define new modeling locations and can also control extrusion or cut endpoints.
- A sweep consists of a profile and a path, which must intersect. A helix combined with a circular profile can quickly create a spring.
- A revolved feature requires a cross-section and an axis of revolution. A regular line can serve as the axis, but construction geometry is easier for SOLIDWORKS to recognize automatically.

### Common Mistakes

- Selecting the wrong direction, model face, or reference plane for Up to Surface and getting an incorrect cut result;
- Creating a reference plane while it is hidden and assuming it was not created;
- Using a sweep path that does not intersect the profile, causing the sweep to fail;
- Looking for Helix and Spiral as a sketch command instead of under Features > Curves;
- Drawing the revolution axis as a regular line and then forgetting to select it manually in the Revolve feature.

### Operation Notes

- File > Save As preserves the previous lesson's model while allowing further practice on a copy.
- Cut-Extrude > End Condition > Up to Surface accepts a model face or reference plane as the cut endpoint.
- Features > Reference Geometry > Plane, select the Front Plane and set a 5 mm offset to create a reference plane.
- Heads-Up View toolbar > Hide/Show Items toggles all reference planes on or off.
- Features > Curves > Helix and Spiral, set Pitch to 5 mm and Revolutions to 10 to create a spring path.
- Insert > Annotations > Cosmetic Thread, select a circular edge with a 10 mm diameter to create an M10 cosmetic thread.

![Lesson 6: Feature creation examples](./images/P11-feature-models-overview.png)

---

## P12 Supplementary Lesson 4: Sketch Planes, Regular Lines, and Construction Geometry

### Core Summary

- A regular 2D sketch can be created only on a reference plane or planar model face, not directly on a cylindrical or other curved face.
- When a feature is needed on a curved location, first create a suitable reference plane. A geometric Tangent relation is more robust than a fixed distance.
- Regular sketch lines participate in feature creation; construction geometry is used only for positioning, constraints, or an axis of revolution and does not form closed contours.

### Common Mistakes

- Attempting to start a regular 2D sketch directly on a cylindrical face;
- Starting a keyway cut at the cylinder center and forgetting to adjust the cut's start position;
- Defining only Tangent and failing to use the Front Plane to control the new plane's orientation;
- Converting an outer contour edge to construction geometry by mistake;
- Deleting the closing regular line that SOLIDWORKS added automatically while editing a revolve sketch.

### Operation Notes

- System Options > Sketch > Auto-rotate view normal to sketch plane on sketch creation and sketch edit (selected) automatically displays a sketch Normal To its plane.

![Supplementary Lesson 4: Tangent reference plane and keyway](./images/P12-tangent-reference-plane-example.png)
![Supplementary Lesson 4: Automatically closed revolve result](./images/P12-revolve-auto-close-result.png)

---

## P13 Lesson 7: Feature Creation, Part 3

### Core Summary

- Revolved Cut removes existing material by rotating a cross-section around an axis. It is unavailable in an empty part because there is no material to remove.
- A reference plane can be defined by up to three point, line, face, or plane references with relations such as Coincident, Parallel, Perpendicular, At Angle, Offset, or Mid Plane.
- Section View and display styles change only how the model is viewed; they do not actually cut or modify the model.
- Fillet and Chamfer can be applied to individual edges or entire faces. More complex cases can use Variable Radius Fillet, Face Fillet, or Full Round Fillet.

### Common Mistakes

- Looking for Revolved Cut in an empty part without first creating solid material;
- Guessing a 12.5 mm offset for the middle of a cube instead of defining a Mid Plane between two faces;
- Continuing to add reference constraints after the plane references already conflict;
- Mistaking Section View for an actual cut feature;
- Selecting an entire face for a fillet or chamfer and unintentionally processing every surrounding edge.

### Operation Notes

- Reference Geometry > Plane > select two opposite faces > Mid Plane creates a center plane through the body.
- Alt+C toggles a newly drawn line between regular geometry and construction geometry.
- Reference Geometry > Plane accepts up to three point, line, face, or plane references.
- Heads-Up View toolbar > Section View temporarily displays the model interior without cutting the solid.
- Hide/Show Items > Sketch Dimensions/Sketch Relations controls the visibility of sketch annotations.
- Features > Fillet/Chamfer, select an edge or face and set the size to process solid edges.

![Lesson 7: Fillet and chamfer results](./images/P13-fillet-chamfer-result.png)

---

## P14 Lesson 8: Feature Creation, Part 4

### Core Summary

- Hole Wizard creates standard holes using hole type, standard, size, end condition, and a position sketch. Position points require dimensions or relations.
- Linear Pattern uses a model edge to control direction and can pattern features or bodies while skipping specified instances.
- Circular Pattern requires an axis of rotation. A reference axis can be defined from references such as the origin and a perpendicular plane.
- Disconnected geometry forms separate bodies. To mirror an entire separated section, use Bodies to Mirror instead of Features to Mirror.

### Common Mistakes

- Selecting a hole type in Hole Wizard but forgetting to switch to Positions and place location points;
- Leaving hole location points blue because they are not dimensioned from edges or reference geometry;
- Selecting the wrong direction edge for a feature pattern or forgetting Reverse Direction;
- Assuming the origin or reference axis does not exist when it is merely hidden;
- Mirroring a disconnected triangular plate as a feature and triggering a disjoint-body error.

### Operation Notes

- Features > Hole Wizard > Hole Type, select the standard, hole type, fastener size, and end condition.
- Hole Wizard > Positions > select a plane > place sketch points to locate one or more holes.
- FeatureManager design tree > hole feature > Edit Feature changes the hole type; Edit Sketch adds or removes position points.
- Features > Linear Pattern, select the direction edge, patterned features, spacing, and instance count.
- Reference Geometry > Axis > select the origin and a model plane to create an axis perpendicular to that plane.
- Mirror > Bodies to Mirror mirrors a separate body that is not connected to the main body.

![Lesson 8: Hole Wizard, pattern, and mirror examples](./images/P14-hole-pattern-mirror-example.png)

---

## P15 Supplementary Lesson 5: Closed Sketch Contours and Selected Contours

### Core Summary

- Extruding an open sketch can create only a thin feature; the interior of a closed sketch forms a closed region that can create a solid feature.
- A model edge is not a sketch line. A region that appears enclosed by model edges can still be an open sketch.
- When a sketch contains multiple closed contours, Selected Contours determines which regions participate in the current feature. The same sketch can also be reused by multiple features.
- A feature can fail with zero-thickness geometry when it touches only at a point or line. Moving the contour slightly or allowing the cut to create separate bodies changes the result.

### Common Mistakes

- Treating model edges as part of the sketch and incorrectly assuming the contour is closed;
- Failing to notice that an open sketch automatically activated Thin Feature and creating an unintended wall;
- Allowing multiple closed regions to preview together without filtering them through Selected Contours;
- Cutting a circle tangent to a model edge and triggering a zero-thickness geometry error;
- Relying on SOLIDWORKS to close a contour automatically without inspecting the line it added.

### Operation Notes

- Sketch > Shaded Sketch Contours (selected) displays closed sketch regions.
- Ctrl+8 displays the sketch Normal To its plane.
- Ctrl+B rebuilds the model and refreshes abnormal display states.
- Feature PropertyManager > Selected Contours, click closed regions to include or exclude them from the feature.
- FeatureManager design tree > select an existing sketch > create a feature to reuse the same sketch in another feature.

![Supplementary Lesson 5: Closed regions and Selected Contours](./images/P15-selected-contours-example.png)

---

## P16 Lesson 9: 3D-Printed Phone Stand

### Core Summary

- The phone stand is built from a primary side profile, then completed with a Mid Plane extrusion, Through All cuts, fillets, and chamfers.
- Structural dimensions should be adjusted for the actual phone width, charging connector, and contact areas rather than copied directly from the example.
- Three bottom contact points define a plane and are less likely than one large printed base surface to rock because of printing inaccuracies.
- Sketch Text can engrave text directly. Sketch Picture and splines can help trace a logo, and each closed region must be selected for a multi-region cut.
- Material density controls Mass Properties results. Evaluate tools measure mass, distance, and angle, and the model can be saved in a neutral format for printing.

### Common Mistakes

- Skipping the project because it appears to use only basic commands and missing Text, Sketch Picture, spline, material, and measurement workflows;
- Failing to measure the actual phone width, causing the stand slot and charging opening not to fit;
- Applying an oversized fillet at the phone contact area, lifting the phone and reducing contact area;
- Leaving a logo spline open or failing to select every closed region, resulting in an incomplete cut;
- Estimating mass with a material of similar density and then treating the result as the exact mass of the printed part.

### Operation Notes

- Extruded Boss/Base > Mid Plane, enter the phone-stand width to extrude the main profile symmetrically.
- Cut-Extrude > Direction 1: Up to Surface > Direction 2: Through All creates a charging opening through both sides.
- Sketch > Text, set the text, font, and size, then Cut-Extrude 0.3 mm to engrave the model surface.
- Tools > Sketch Tools > Sketch Picture inserts an image and adjusts its transparency, size, and position.
- Spline > right-click > Show Control Polygon displays control points for reshaping the curve.
- FeatureManager design tree > Material > right-click > Edit Material sets the material density used for mass estimation.
- Evaluate > Mass Properties/Measure displays model mass, distance, and angle.
- File > Save As > STEP exports the print-delivery format used in the course.

![Lesson 9: 3D-printed phone stand model](./images/P16-phone-stand-model.png)

---

## P17 Supplementary Lesson 8: Editing Features and Resolving Errors

### Core Summary

- For simple changes, double-click a sketch dimension or feature dimension. For complex changes, use Edit Sketch or Edit Feature.
- Selecting a face generated by a feature in the graphics area helps locate the corresponding feature in the FeatureManager design tree.
- After an upstream sketch changes, downstream fillets, chamfers, and other features can lose their original edge or face references and report errors.
- Troubleshoot by editing the feature that reports the error, inspecting missing references, and deleting or replacing them with new edges or faces.

### Common Mistakes

- Looking only for dimensions on the finished model surface without determining whether the change belongs to the sketch or the extrusion depth;
- Clicking a fillet face and assuming the original extrude feature was selected;
- Rebuilding the entire model after seeing a yellow warning icon instead of first editing the failed feature;
- Keeping a red dashed reference that no longer exists after changing an upstream contour;
- Fixing the first error but ignoring subsequent failed features.

### Operation Notes

- Double-click a sketch dimension > enter a new value > Ctrl+B quickly changes the dimension and rebuilds the model.
- FeatureManager design tree > Sketch > Edit Sketch opens the sketch for coordinated changes to dimensions and contours.
- Double-click a feature dimension, or feature > Edit Feature, to change parameters such as extrusion depth.
- Graphics area > select a face created by a feature to locate the corresponding feature in the FeatureManager design tree.
- Failed feature > Edit Feature > remove missing references > reselect edges or faces to repair dangling references.

![Supplementary Lesson 8: Modified phone stand model](./images/P17-modified-phone-stand-model.png)

---
