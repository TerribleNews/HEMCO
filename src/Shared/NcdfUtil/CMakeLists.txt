add_library(NcdfUtilHco STATIC EXCLUDE_FROM_ALL
	m_do_err_out.F90
	m_netcdf_io_checks.F90
	m_netcdf_io_close.F90
	m_netcdf_io_create.F90
	m_netcdf_io_define.F90
	m_netcdf_io_get_dimlen.F90
	m_netcdf_io_handle_err.F90
	m_netcdf_io_open.F90
	m_netcdf_io_read.F90
	m_netcdf_io_readattr.F90
	m_netcdf_io_write.F90
	ncdf_mod.F90
)
# NOTE: File julday_mod.F90 is included only for use in GEOS which
# uses separate CMake files.
target_link_libraries(NcdfUtilHco
	PUBLIC JulDayHco HeadersHco
)
target_include_directories(NcdfUtilHco
	INTERFACE ${HEMCO_BINARY_DIR}/mod
)
