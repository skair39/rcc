# world modeling application
# brl/bbas/bwm/video/CMakeLists.txt


SET(bwm_video_sources
   dll.h

   bwm_video_cam_istream.cxx     bwm_video_cam_istream.h   bwm_video_cam_istream_sptr.h
   bwm_video_cam_ostream.cxx     bwm_video_cam_ostream.h   bwm_video_cam_ostream_sptr.h
   bwm_video_corr.cxx            bwm_video_corr.h          bwm_video_corr_sptr.h
   bwm_video_site_io.cxx         bwm_video_site_io.h
                                 bwm_video_site_io_defs.h
   bwm_video_corr_processor.cxx  bwm_video_corr_processor.h
   bwm_video_registration.cxx    bwm_video_registration.h
)

AUX_SOURCE_DIRECTORY(Templates bwm_video_sources)
ADD_LIBRARY(bwm_video ${bwm_video_sources})

TARGET_LINK_LIBRARIES( bwm_video vidl brip vil vbl vgl vul vpl vsl vgl_algo vnl_algo vnl bsta bsol expatpp vsol vpgl vpgl_algo)

IF(BUILD_TESTING)
  SUBDIRS(tests)
ENDIF(BUILD_TESTING)

SUBDIRS(exe)


