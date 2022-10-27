Animations are stored in AnimationClip assets and are usually found in files with AnimatorController and Animation assets.

AnimatorControllers are containers for clips and can blend between them. Sb3UGS has two editors for AnimatorControllers. The first editor opens with a double click.
![Wiki_-_animations_-_01](https://user-images.githubusercontent.com/104311725/167838075-d886be56-def1-4da1-b9d7-7026adc0773c.png)


No track information can be shown in that state because it requires the skeleton to resolve the hashes stored in the AnimationClip. Open a file with that information. This is available in every piece of clothes, but incomplete. So for a complete resolution open the base body Animator. Then link the AnimatorController to that Animator with the drop down box.

![wiki - animations - 02](https://user-images.githubusercontent.com/104311725/198281768-4c9c18bc-0a15-488f-8c38-13db7e796533.png)

Since the AnimationClip is still selected the animation track information can be displayed. Sb3UGS does not resolve directly from the skeleton in the Animator, but uses the Animator's Avatar for this. In case that tracks are unknown the Avatar of that Animator needs to be corrected. With the tracks correctly shown Sb3UGS is prepared for further operations, like the preview in the [Introduction](https://github.com/enimaroah-cubic/Sb3UGS/wiki#introduction), export and replacement of animations.

At the bottom of the image at the top the Controller button is shown. It opens the second editor for the same AnimatorController. In most cases the StateMachine tab is required to make required changes for modding. And even that tab does not allow to fully edit the controller.

![Wiki_-_animations_-_03](https://user-images.githubusercontent.com/104311725/167838375-9e3fbd9a-f2c7-4250-8fa5-0e2cb8b8cd60.png)

Back to the first editor. After editing animations in a 3d editor, dragging the ImportedAnimation from the workspace onto a target AnimationClip shows the following dialog for replacement.

![Wiki_-_animations_-_04](https://user-images.githubusercontent.com/104311725/167838461-844101b7-2df3-4907-958b-57ef541127d0.png)