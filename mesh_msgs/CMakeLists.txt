cmake_minimum_required(VERSION 3.5)
project(mesh_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)

find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)

set(msg_files
  "msg/MeshFaceCluster.msg"
  "msg/MeshFaceClusterStamped.msg"
  "msg/MeshMaterial.msg"
  "msg/MeshGeometry.msg"
  "msg/MeshGeometryStamped.msg"
  "msg/MeshMaterials.msg"
  "msg/MeshMaterialsStamped.msg"
  "msg/MeshVertexColors.msg"
  "msg/MeshVertexColorsStamped.msg"
  "msg/MeshVertexCosts.msg"
  "msg/MeshVertexCostsStamped.msg"
  "msg/MeshTexture.msg"
  "msg/MeshTriangleIndices.msg"
  "msg/VectorField.msg"
  "msg/VectorFieldStamped.msg"
  "msg/MeshVertexTexCoords.msg"
)

set (srv_files
  "srv/GetGeometry.srv"
  "srv/GetLabeledClusters.srv"
  "srv/GetMaterials.srv"
  "srv/GetTexture.srv"
  "srv/GetUUIDs.srv"
  "srv/GetVertexColors.srv"
  "srv/GetVertexCosts.srv"
  "srv/GetVertexCostLayers.srv"
)

  rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES
  geometry_msgs
  sensor_msgs
  std_msgs
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
