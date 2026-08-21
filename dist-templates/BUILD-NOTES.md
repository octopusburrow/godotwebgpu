# Web template build — 2026-08-21, Burrow (WSL2, emsdk latest)
- Source: dwalter/godotwebgpu @ webgpu-4.6.2, scons platform=web target=template_release webgpu=yes
- One compat patch needed vs current emsdk/emdawnwebgpu: `_fence_work_done_callback` in
  drivers/webgpu/rendering_device_driver_webgpu.cpp needs the 4-param signature
  (WGPUQueueWorkDoneStatus, WGPUStringView message, void*, void*) — newer Dawn added the
  message param to WGPUQueueWorkDoneCallback.
