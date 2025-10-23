^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package leo_camera
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.3.0 (2025-05-22)
------------------
* Update rosdep rules: use libcamera0.5
* Merge pull request `#124 <https://github.com/fictionlab/leo_camera_ros/issues/124>`_ from ahcorde/ahcorde/rolling/replace_ament_target_dependencies
  Replace ament_target_dependencies with target_link_libraries
* Replace ament_target_dependencies with target_link_libraries
* Merge pull request `#121 <https://github.com/fictionlab/leo_camera_ros/issues/121>`_ from christianrauch/coredumps
  add documentatin on how to generate core dumps
* add documentatin on how to generate core dumps
* Merge pull request `#116 <https://github.com/fictionlab/leo_camera_ros/issues/116>`_ from tschuette22/feat-frame_id-parameter
  Add Camera frame_id Parameter to Node
* feat: add parameter for frame_id of the camera
* Merge pull request `#123 <https://github.com/fictionlab/leo_camera_ros/issues/123>`_ from christianrauch/fix_etm_default_manual
  only restore 'ExposureTime' if it is not set
* only restore 'ExposureTime' if it is not set and has been stored before
* Merge pull request `#119 <https://github.com/fictionlab/leo_camera_ros/issues/119>`_ from christianrauch/update_dbg_doc
  extend trouble shooting instructions
* include instructions for installing debug symbols for binary bloom packages
* automatically generate backtrace in gdb trouble shooting instructions
* fix table column width
* Merge pull request `#114 <https://github.com/fictionlab/leo_camera_ros/issues/114>`_ from christianrauch/orientation
  orientation parameter
* document new "orientation" parameter
* remove trailig white space
* new parameter for camera orientation in 90 degree steps
* fetch "camera" parameter once directly from declaration and reuse
* Contributors: Alejandro Hernandez Cordero, Błażej Sowa, Christian Rauch, Jan Hernas, Tjark

0.1.0 (2025-04-03)
------------------
* Add file with custom rosdep rules
* Reset version
* Change project name to leo_camera
* Remove on set param handler in camera_node
* Remove flake8 residue
* Remove python dependencies
* Add pkg-config to buildtool dependencies
* Remove compressed image publishing
* Rename package to leo_camera_ros
* Merge pull request `#100 <https://github.com/fictionlab/leo_camera_ros/issues/100>`_ from larsll/scale-raw
  Enable selection of sensor format to avoid a cropped FoV
* Enable selection of sensor resolution
* Merge pull request `#101 <https://github.com/fictionlab/leo_camera_ros/issues/101>`_ from christianrauch/declare_read
  read parameters role, width, and height at declaration
* read parameters 'role', 'width', and 'height' at declaration
  These parameters are read-only. We can read them directly when they are
  declared. This avoids referencing the parameter name in multiple places,
  'declare_parameter' and 'get_parameter', and thus avoids one additional
  parameter lookup.
* Merge pull request `#98 <https://github.com/fictionlab/leo_camera_ros/issues/98>`_ from christianrauch/ignore_invalid_def
  Ignore invalid default values
* ignore scalar default values for span controls
  Previously, when a span control was declared with a scalar default value,
  we ignored the whole control. Instead, ignore only the default value and
  declare the control without an initial value, such that a user can still
  set the control.
* Merge pull request `#57 <https://github.com/fictionlab/leo_camera_ros/issues/57>`_ from christianrauch/parameter_handler
  dedicated class and library for parameter handling
* redeclare implicitly undeclared parameters
* dedicated classes for parameter handling and conflict resolution
  The node declares and initialises all camera controls with their default
  control value. However, some libcamera IPAs have a peculiar behaviour, such
  as incompatible control and default value types and conflicting default
  control values.
  These kinds of cases were previously handled in 'resolve_conflicts' and
  'check_conflicts'. This moves the functionality and the general parameter
  handling to the classes 'ParameterHandler', for general handling of camera
  controls and their respective parameters, and 'ParameterConflictHandler',
  for handling and resolving conflicts of the camera controls.
* Merge pull request `#96 <https://github.com/fictionlab/leo_camera_ros/issues/96>`_ from christianrauch/ae_unset
  assume enabled for unset auto exposure
* assume enabled for unset auto exposure
  If control 'AeEnable' does not have a default value, we would assume that
  it is "off", setting the 'ExposureTime' by default. If the default
  'ExposureTime' is low, this leads to underexposed images by default.
  Fix this by assuming that 'AeEnable' is always explicitly disabled and
  assume enabled by default.
* constrain log settings to node namespace
* Merge pull request `#90 <https://github.com/fictionlab/leo_camera_ros/issues/90>`_ from samyarsadat/ci_file_url_param
  Add ROS parameter for setting camera info file URL
* Added ROS parameter for setting camera calibration info file URL.
* Merge pull request `#93 <https://github.com/fictionlab/leo_camera_ros/issues/93>`_ from samyarsadat/def_val_fix
  Ensure fixed-extent span controls with None defaults aren't skipped
* Ensure that a span control is not skipped because its default value is scalar when the default is None. None defaults are handled by cv_to_pv().
* Merge pull request `#88 <https://github.com/fictionlab/leo_camera_ros/issues/88>`_ from samyarsadat/minor_fixes
  Add array bounds check in pv_to_cv_int_array
* Added array length check to vector -> Point, Size, Rectangle conversions.
* Merge pull request `#89 <https://github.com/fictionlab/leo_camera_ros/issues/89>`_ from christianrauch/check_span_default
  prevent setting a scalar default value for span controls
* turn exception into warning
* prevent setting a scalar default value for span controls
* Merge pull request `#86 <https://github.com/fictionlab/leo_camera_ros/issues/86>`_ from christianrauch/ignore_jpeg_param
  ignore "jpeg_quality" parameter for MJPEG streams
* ignore "jpeg_quality" parameter for MJPEG streams
* Merge pull request `#84 <https://github.com/fictionlab/leo_camera_ros/issues/84>`_ from christianrauch/r16
  add format mapping for 16bit grey scale and colour
* add format mapping for 16bit grey scale and colour
* Merge pull request `#82 <https://github.com/fictionlab/leo_camera_ros/issues/82>`_ from christianrauch/refine_exceptions
  refine exceptions
* use invalid_conversion for mismatching bound types
* add exceptions for unknown and unsupported controls
* use should_not_reach exception for unhandled type in switch statement
* Merge pull request `#78 <https://github.com/fictionlab/leo_camera_ros/issues/78>`_ from christianrauch/update_doc
  update build documentation
* automatically install rosdep resolved packages
* add "--rosdistro" to cover cases where no packages have been installed yet
* build with direct console output
* install colcon-meson for libcamera
* Merge pull request `#77 <https://github.com/fictionlab/leo_camera_ros/issues/77>`_ from christianrauch/release_0.3
  bump the minor version for a new release
* bump the minor version for a release with libcamera 0.4 support and fixes
* Merge pull request `#40 <https://github.com/fictionlab/leo_camera_ros/issues/40>`_ from christianrauch/faq
  troubleshooting common issues
* info about common camera detection and buffer allocation issues
* update camera_ros build instructions
* libcamera install & build instructions
* make binary package installation ROS distro agnostic
* separete binary and source installation
* link the image_pipeline repo
* fix static parameter table alignment
* change new default 'role' in documentation
* Merge pull request `#76 <https://github.com/fictionlab/leo_camera_ros/issues/76>`_ from christianrauch/fix_format
  change default stream role
* change default role to 'viewfinder' for better stream format defaults
* separate exceptions for configuration errors
* remove redundant "Pixelformat" print
* remove redundant printing of stream pixel formats and sizes
* fix typo
* show stream configuration before determining pixel format
* add info about role configuration
* assert that only one StreamConfiguration is generated for the requested role
* Merge pull request `#75 <https://github.com/fictionlab/leo_camera_ros/issues/75>`_ from christianrauch/new_control_types
  support new control types
* implement support for new control types
* replace streaming operator with function to avoid conflicting definition
* cv_to_pv_scalar for unsigned integer
* move custom exceptions to dedicated header file
* replace 'is_arithmetic' with 'is_constructible' to determine template match
* move LIBCAMERA_VER_GE macro to dedicated header file
* fix typo
* Merge pull request `#74 <https://github.com/fictionlab/leo_camera_ros/issues/74>`_ from christianrauch/almalinux8
  add AlmaLinux 8 and fix warnings
* add clang-format as manual test dependency
* manual build and test steps
* add AlmaLinux 8
* remove PIP_BREAK_SYSTEM_PACKAGES
* remove extra ';' after macro
* Merge pull request `#73 <https://github.com/fictionlab/leo_camera_ros/issues/73>`_ from christianrauch/ci_almalinux
  add AlmaLinux to CI
* add AlmaLinux to CI
* remove unused checkout
* remove dedicated linting via third-party colcon lint
* replace virtual environment with PIP_BREAK_SYSTEM_PACKAGES
* Merge pull request `#71 <https://github.com/fictionlab/leo_camera_ros/issues/71>`_ from christianrauch/optional_image_view
  optional image view dependency
* version 0.2.1
* ignore 'image_view' runtime dependency on humble
* make the 'image_view' package optional in the launch file
* require at least libcamera 0.1 by manifest
* Merge pull request `#70 <https://github.com/fictionlab/leo_camera_ros/issues/70>`_ from christianrauch/thread_fixes
  thread and control fixes
* do not set parameters without value
* check that 'AeEnable' is set
* always add unset parameters to initial list to know supported controls
* export 'camera_component'
* remove non-existing include paths
* use unique_lock to detect potential deadlock
* add condition_variable to synchronise producer and consumer thread
* remove unused header
* move namespace shortcut
* Merge pull request `#66 <https://github.com/fictionlab/leo_camera_ros/issues/66>`_ from christianrauch/param_atomic
  set parameters atomically
* version 0.2.0
* bump CMake version to minimum version for humble (REP 2000)
* set global 'running' flag only once
* debug the parameters that are actually applied as controls to the request
* only override parameters that have matching controls
* set parameters atomically
* remove setting of read-only parameters
* Merge pull request `#62 <https://github.com/fictionlab/leo_camera_ros/issues/62>`_ from christianrauch/fix_control_exception
  fix control exception
* move 'compressImageMsg' before class implementation
* show warning for not yet handled controls
* optimise includes via IWYU
* link libcamera to utils object
* Merge pull request `#15 <https://github.com/fictionlab/leo_camera_ros/issues/15>`_ from christianrauch/fix_dynamic_extent
  handle dynamic extents
* check for supported parameter value type based on control id and not value
  libcamera 'Control<T>' and their related 'ControlInfo' do not necessarily
  have the same control and value types. This previously caused issues when
  an unsupported control type, such as a span of a complex type, is mapped
  to a ROS parameter via the type of the default 'ControlValue'.
  Fix this by using the the actual control type, regardless of the types of
  the values in the 'ControlInfo'.
* remove array flag from 'cv_to_pv_type' and determine this via the extent
* clarify the value range and meaning of the extracted ControlId extent
  Previously 'get_extent' would return the original 'extent' of a Span and 0
  for non-span controls. This is ambiguous as an extent of 0 means that the
  original control type is either not a span or an empty span that can store
  no elements.
  Resolve this ambiguity by enforcing that libcamera controls cannot contain
  empty spans via a compile time assertion and clarify that an extent of 0
  is only returned for non-span types.
* remove redundant ';'
* remove 'colcon-ros' as manual dependency
* handle dynamic extents in array size check
* implement scalar-array less and greater comparison
* handle invalid conversion of non-arithmetic types via custom exception
* handle dynamic extents in parameter description
* use the actual vector size in control value conversion
  Dynamic Spans have a maximum extent ('dynamic_extent') but their associated
  'ControlInfo' can contain a variable number of elements. For dynamic Spans
  with a single element in the default 'ControlValue', this previously caused
  the exception 'std::length_error' since a vector with "maximum extent"
  elements was constructed.
  Fix this by ignoring the extent and using the actual number of elements.
* Merge pull request `#55 <https://github.com/fictionlab/leo_camera_ros/issues/55>`_ from christianrauch/dbg_default_config
  add debugging information for pixel format selection
* make camera and pixel format configurable in launch file
* more documentation on pixel formats
* add more log messages for pixel format selection
* fix typo 'silent' -> 'silence'
* Merge pull request `#52 <https://github.com/fictionlab/leo_camera_ros/issues/52>`_ from christianrauch/doc_interfaces
  document the node interfaces, including calibration
* add information on how to enable and show debug information
* document the node interfaces, including calibration
* Merge pull request `#48 <https://github.com/fictionlab/leo_camera_ros/issues/48>`_ from christianrauch/jazzy_ci
  Ubuntu 24.04 CI
* add Ubuntu 24.04 to CI
* install colcon-lint in a virtual environment
* colcon-lint
* add 'rclcpp' as dependency
* Merge pull request `#49 <https://github.com/fictionlab/leo_camera_ros/issues/49>`_ from christianrauch/fix_leaks
  fix memory leaks on destruction
* free allocator and stream
* free camera before stopping the camera manager
* Merge pull request `#25 <https://github.com/fictionlab/leo_camera_ros/issues/25>`_ from christianrauch/jazzy
  updates for Ubuntu 24.04
* import LaunchDescription directly
* remove line length limits
* lock instead of try_lock
* remove the 'qos_event.hpp' header
* include guard for cv_bridge header
* Merge pull request `#47 <https://github.com/fictionlab/leo_camera_ros/issues/47>`_ from christianrauch/default_configuration
  use default stream configuration if supported by the ROS message
* use default stream configuration if supported by the ROS message
* Merge pull request `#44 <https://github.com/fictionlab/leo_camera_ros/issues/44>`_ from christianrauch/threads
  use processing threads
* use processing threads
* Merge pull request `#46 <https://github.com/fictionlab/leo_camera_ros/issues/46>`_ from christianrauch/linting
  linting
* fix Python linting issues in launch file
* add more linters
* Merge pull request `#43 <https://github.com/fictionlab/leo_camera_ros/issues/43>`_ from christianrauch/nv
  add NV formats
* use macro for conversion template definition
* turn all warnings into errors
* show error in case of conversion issues from cv_bridge
* add format mappings for NV21 and NV24
* Merge pull request `#27 <https://github.com/fictionlab/leo_camera_ros/issues/27>`_ from christianrauch/documentation
  add documentation
* ignore changes to the README
* add instructions for installation, usage and configuration via parameters
* example launch file
* Merge pull request `#39 <https://github.com/fictionlab/leo_camera_ros/issues/39>`_ from christian-nils/fix_camera_controls_init
  fix: the initial camera controls not used when starting camera
* fix: the initial camera controls not used when starting camera
  fixes issues such as https://github.com/christianrauch/camera_ros/issues/37 where the sink camera does is not aware of the targeted framerate causing problems with the autoexposure algorithm.
* Merge pull request `#31 <https://github.com/fictionlab/leo_camera_ros/issues/31>`_ from christianrauch/new_controls
  handle new camera controls in libcamera 0.2
* handle new camera controls in libcamera 0.2
* Merge pull request `#28 <https://github.com/fictionlab/leo_camera_ros/issues/28>`_ from christianrauch/common_pixel_format
  check and show pixel formats supported by the camera and the ROS message
* check and show pixel formats supported by the camera and the ROS message
* hint on which parameters to set to silent warnings
* require at least libcamera 0.1
* Merge pull request `#23 <https://github.com/fictionlab/leo_camera_ros/issues/23>`_ from tosbaja/compression_quality
  functionality for compression quality
* functionality for compression quality
* Merge pull request `#16 <https://github.com/fictionlab/leo_camera_ros/issues/16>`_ from christianrauch/ci
  add CI pipeline
* build and test 'camera_ros' package on 'humble'
* version 0.1.0
* de-/compress on demand
* pre-mmap buffers
* header changes suggested by IWYU
* separate pretty printing functions for libcamera objects
* separate format mapping
* predefine min/max templates for arithmetic types
* restrict min/max templates to ControlType enums
* separate parameter conflict checks
* make stream role configurable
* error on valid pixel formats that are unsupported by the camera
* set endianness
* show streaming formats and resolutions when no have been selected
* select camera by id or name
* synchronise callbacks
* dynamic configuration with libcamera exposed control values
* reuse cancelled requests
* clang-format break after return type
* update to C++17
* package description
* show available cameras
* make camera ID configurable
* set image dimensions and format parameters after successfull configuration
* publish raw/compressed counterpart image via cv_bridge
* integrate camera info manager and publish camera info
* use shared image messages to allow intra process communication
* configurable image width and height
* automatic selection of supported pixel format
* handle 'YUYV' format and publish the raw image
* configuration of streaming buffer pixel format
* show all supported streaming and pixel format configurations at startup
* publish compressed image
* open first camera with default settings
* implement as composable node with standalone node executable
* apply format
* enable clang-format test with custom style
* link libcamera
* add MIT LICENSE
* camera_ros
* Contributors: Błażej Sowa, Christian Rauch, Christian-Nils Boda, Emre Kuru, Jan Hernas, Samyar Sadat Akhavi, Woojin Wie
