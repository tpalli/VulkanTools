Here is a list of all supported features in VkTrace, followed by a TODO list of features that we'd like to add soon in the development process. We've also listed the features that we'd "like to have" in the future, but don't have a short-term plan to implement. 

Feel Free to vote things up in the lists, attempt to implement them yourself, or add to the list!

As you complete an item, please copy / paste it into the SUPPORTED FEATURES section.

**SUPPORTED FEATURES IN DEBUGGER**
* Generating & loading traces
* Replay traces within the UI w/ pause, continue, stop ability
  * Auto-pause on Validation Layer Messages (info, warnings, and/or errors), controlled by settings
  * Single-step the replay
  * Timeline pointer gets updated in real-time of replayed API call
  * Run the replay in a separate thread from the UI
  * Pop-out replay window to be floating so it can replay at larger dimensions
* Timeline shows CPU time of each API call
  * A separate timeline is shown for each thread referenced in the trace file
  * Tooltips display the API call index and entrypoint name and parameters
  * Click call will cause API Call Tree to highlight call
* API entrypoints names & parameters displayed in UI
* Tracing and replay standard output gets directed to Output window
* Plugin-based UI allows for extensibility to other APIs
* Search API Call Tree
  * Search result navigation
* API Call Tree Enhancements:
  * Draw call navigation buttons
  * Draw calls are shown in bold font
  * "Run to here" context menu option to control where Replayer pauses
* Group API Calls by:
  * Frame boundary
  * Thread Id
* Export API Calls as Text file
* Settings dialog

**TODO LIST IN DEBUGGER**
* Hide / show columns on API Call Tree
* State dependency graph at selected API Call
* Group API Calls by:
  * API-specific debug groups
  * Command Buffer Submission
  * Render vs State calls
* Saving 'session' data:
  * Recently loaded traces
* Capture state from replay
* Rewind the replay
* Custom viewers of each state type
* Per API entrypoint call stacks
* Collect and display machine information
* 64-bit build supports 32-bit trace files
* Timeline enhancements:
  * Pan & Zoom
* Optimize trace file loading by memory-mapping the file

**SUPPORTED FEATURES IN TRACING/REPLAYING COMMAND LINE TOOLS AND LIBRARIES**
* Command line Tracer app (vktrace) which launches game/app with tracing library(ies) inserted and writes trace packets to a file
* Command line Tracer server which collects tracing packets over a socket connection and writes them to a file
* Vulkan tracer library supports multithreaded Vulkan apps
* Command line Replayer app (vkreplay) replays a Vulkan trace file with Window display on Linux

**TODO LIST IN TRACING/REPLAYING COMMAND LINE TOOLS AND LIBRARIES**
* Optimize replay speed by using hash maps for opaque handles
* Handle XGL persistently CPU mapped buffers during tracing, rather then relying on updating data at unmap time
* Optimize Replayer speed by memory-mapping the file and/or reading file in a separate thread
* Looping in Replayer over arbitrary frames or calls
* Looping in Replayer with state restoration at beginning of loop
* Replayer window display of Vulkan on Windows OS
* Command line tool to display trace file in human readable format
* Command line tool for editing trace files in human readable format
* Replayer supports multithreading
* 64-bit build supports 32-bit trace files
* XGL tracing and replay cross platform support with differing GPUs

**LIKE TO HAVE FUTURE FEATURE IDEAS**
* Export trace file into *.cpp/h files that compile into a runnable application
* Editing, adding, removal of API calls
* Shader editing
* Hyperlink API Call Tree to state-specific windows


**EXTENSION STATUS**
| Extension Name                         |Pub Intro |Priv Intro   | Status   | Notes               |
|----------------------------------------|:----------:|:-----------:|:--------:|:-------------------:|
| VK_KHR_android_surface                 | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_display                         | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_display_swapchain               | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_surface                         | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_swapchain                       | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_wayland_surface                 | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_win32_surface                   | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_xcb_surface                     | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_xlib_surface                    | 1.0.3.1  |             | DONE     |                     |
| VK_KHR_mir_surface                     | 1.0.3.1  |             | DONE     |                     |
| VK_EXT_debug_report                    | 1.0.3.1  |             | DONE     |                     |
| VK_MVK_moltenvk                        | 1.0.3.1  |             | NOT DONE | Apple only, will not implement. |
| VK_MVK_ios_surface                     | 1.0.3.1  |             | NOT DONE | IOS only, will not implement.   |
| VK_MVK_macos_surface                   | 1.0.3.1  |             | NOT DONE | MacOS only, will not implement. |
| VK_AMD_rasterization_order             | 1.0.13.0 |             | DONE     |                     |
| VK_EXT_debug_marker                    | 1.0.13.0 |             | DONE     | Supported           |
| VK_AMD_gcn_shader                      | 1.0.21.0 |             | DONE     |                     |
| VK_AMD_shader_trinary_minmax           | 1.0.21.0 |             | DONE     |                     |
| VK_IMG_format_pvrtc                    | 1.0.24.0 |             | NOT DONE | Spec not published  |
| VK_AMD_draw_indirect_count             | 1.0.26.0 |             | DONE     |                     |
| VK_AMD_gpu_shader_half_float           | 1.0.30.0 |             | DONE     |                     |
| VK_AMD_negative_viewport_height        | 1.0.30.0 |             | DONE     |                     |
| VK_AMD_shader_ballot                   | 1.0.30.0 |             | DONE     |                     |
| VK_EXT_validation_flags                | 1.0.30.0 |             | DONE     |                     |
| VK_NVX_device_generated_commands       | 1.0.37.0 |1.0.39.0.next| NOT DONE | Complex to impl     |
| VK_KHR_get_physical_device_properties2 | 1.0.39.0 |1.0.32.0.next| NOT DONE | Need to implement   |
| VK_KHX_device_group                    | 1.0.39.0 |1.0.32.0.next| NOT DONE | Need to implement   |
| VK_KHR_maintenance1                    | 1.0.39.0 |1.0.32.0.next| UNTESTED | Need to test        |
| VK_KHR_shader_draw_parameters          | 1.0.39.0 |1.0.32.0.next| UNTESTED | Should "just work"  |
| VK_EXT_acquire_xlib_display            | 1.0.39.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_EXT_direct_mode_display             | 1.0.39.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_EXT_shader_subgroup_ballot          | 1.0.39.0 |             | DONE     |                     |
| VK_EXT_shader_subgroup_vote            | 1.0.39.0 |             | DONE     |                     |
| VK_EXT_swapchain_colorspace            | 1.0.39.0 |             | DONE     |                     |
| VK_EXT_display_control                 | 1.0.39.0 |             | NOT DONE | Need to implement   |
| VK_EXT_display_surface_counter         | 1.0.39.0 |             | NOT DONE | Need to implement   |
| VK_NN_vi_surface                       | 1.0.39.0 |             | NOT DONE | Nintendo only, will not implement.|
| VK_KHR_push_descriptor                 | 1.0.42.0 |1.0.32.0.next| NOT DONE | Need to implement   |
| VK_KHX_device_group_creation           | 1.0.42.0 |1.0.32.0.next| NOT DONE | Need to implement   |
| VK_NV_external_memory                  | 1.0.42.0 |1.0.38.0.next| NOT DONE | May "just work"     |
| VK_NV_external_memory_capabilities     | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_NV_external_memory_win32            | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_memory_capabilities    | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_memory_fd              | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_memory_win32           | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_semaphore_capabilities | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_semaphore_fd           | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_semaphore_win32        | 1.0.42.0 |1.0.38.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_memory                 | 1.0.42.0 |1.0.38.0.next| -        | Should "just work"  |
| VK_KHR_external_semaphore              | 1.0.42.0 |1.0.38.0.next| -        | Should "just work"  |
| VK_KHX_multiview                       | 1.0.42.0 |1.0.38.0.next| -        | Should "just work"  |
| VK_KHR_win32_keyed_mutex               | 1.0.42.0 |1.0.38.0.next| UNTESTED | Should "just work"  |
| VK_NV_win32_keyed_mutex                | 1.0.42.0 |1.0.39.0.next| NOT DONE | May "just work"     |
| VK_NV_clip_space_w_scaling             | 1.0.42.0 |             | NOT DONE |                     |
| VK_NV_geometry_shader_passthrough      | 1.0.42.0 |             | NOT DONE | May "just work"     |
| VK_NV_sample_mask_override_coverage    | 1.0.42.0 |             | NOT DONE | May "just work"     |
| VK_NV_viewport_array2                  | 1.0.42.0 |             | NOT DONE | May "just work"     |
| VK_NV_viewport_swizzle                 | 1.0.42.0 |             | NOT DONE | May "just work"     |
| VK_NVX_multiview_per_view_attributes   | 1.0.42.0 |             | NOT DONE | May "just work"     |
| VK_EXT_discard_rectangles              | 1.0.42.0 |             | NOT DONE | Need to implement   |
| VK_EXT_hdr_metadata                    | 1.0.42.0 |             | NOT DONE | Need to implement   |
| VK_KHR_descriptor_update_template      | 1.0.42.0 |             | UNTESTED | Need to test        |
| VK_KHR_variable_pointers               | 1.0.42.0 |             | UNTESTED | Should "just work"  |
| VK_KHR_incremental_present             | 1.0.46.0 |1.0.38.0.next| -        | Should "just work"  |
| VK_GOOGLE_display_timing               | 1.0.46.0 |             | NOT DONE | Need to implement   |
| VK_KHR_get_display_properties2         |          |1.0.47.0.next| NOT DONE | Need to implement.  |
| VK_KHX_subgroup                        |          |1.0.47.0.next| -        | Should "just work"  |
| VK_KHR_shared_presentable_image        | 1.0.49.0 |1.0.32.0.next| NOT DONE | Need to implement   |
| VK_KHR_get_surface_capabilities2       | 1.0.49.0 |1.0.47.0.next| UNTESTED | Need to test        |
| VK_KHR_maintenance2                    |          |1.0.49.0.next| NOT DONE | Should "just work". New image creation flags may affect vkCreateImage tracing. |
| VK_KHX_depth_stencil_layouts           |          |1.0.49.0.next| NOT DONE | Need to implement   |
| VK_AMD_texture_gather_bias_lod         | 1.0.51.0 |             | DONE     |                     |
| VK_KHR_external_fence_capabilities     | 1.0.54.0 |1.0.47.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_fence_fd               | 1.0.54.0 |1.0.47.0.next| NOT DONE | Need to implement   |
| VK_KHR_external_fence_win32            | 1.0.54.0 |1.0.47.0.next| NOT DONE | Need to implement   |
| VK_KHR_get_memory_requirements2        | 1.0.54.0 |1.0.47.0.next| NOT DONE | Need to implement   |
| VK_KHR_16bit_storage                   | 1.0.54.0 |1.0.47.0.next| -        | Should "just work"  |
| VK_KHR_external_fence                  | 1.0.54.0 |1.0.47.0.next| -        | Should "just work"  |
| VK_KHR_storage_buffer_storage_class    | 1.0.54.0 |1.0.47.0.next| -        | Should "just work"  |
| VK_KHR_sampler_filter_minmax           | 1.0.54.0 |1.0.49.0.next| DONE     |                     |
| VK_NV_dedicated_allocation             | 1.0.54.0 |1.0.49.0.next| NOT DONE | May "just work"     |
| VK_KHR_dedicated_allocation            | 1.0.54.0 |1.0.49.0.next| -        | Should "just work"  |
| VK_AMD_gpu_shader_int16                | 1.0.54.0 |             | DONE     |                     |
| VK_NV_fill_rectangle                   | 1.0.54.0 |             | NOT DONE | May "just work"     |
| VK_NV_fragment_coverage_to_color       | 1.0.54.0 |             | NOT DONE | May "just work"     |
| VK_NV_framebuffer_mixed_samples        | 1.0.54.0 |             | NOT DONE | May "just work"     |
| VK_EXT_blend_operation_advanced        | 1.0.54.0 |             | UNTESTED | Need to test        |
| VK_KHR_bind_memory2                    |          |1.0.56.0.next| NOT DONE | New functions. Should mostly "just work" |
| VK_KHR_protected_memory                |          |1.0.56.0.next| NOT DONE | Need to investigate protecting memory in trace file |
| VK_KHR_sampler_ycbcr_conversion        |          |1.0.56.0.next| NOT DONE | New functions. Should mostly "just work" |
| VK_KHR_image_format_list               |          |1.0.56.0.next| NOT DONE | Should "just work". New image creation flags may affect vkCreateImage tracing. |
| VK_KHR_relaxed_block_layout            | ?        |1.0.56.0.next| UNTESTED | Should "just work"  |
| VK_IMG_filter_cubic                    | 1.0.8.0  |             | DONE     |                     |
| VK_NV_glsl_shader                      | 1.0.8.0  |             | NOT DONE | May "just work"     |
| VK_KHR_sampler_mirror_clamp_to_edge    | 1.0.8.0  |             | UNTESTED | Should "just work"  |
| VK_AMD_shader_explicit_vertex_parameter| 1.0.21.0 |             | DONE     |                     |
