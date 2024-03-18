# Uncomment the next line to define a global platform for your project
platform :ios, '13.0'
source 'https://github.com/CocoaPods/Specs.git'
deployment_target = '13.0'


# This is work wersion !
#pod 'YandexMobileAdsInstream', '~> 0.11.0'

pod 'GoogleAds-IMA-iOS-SDK'
pod 'YandexMobileAdsInstream'

target 'ProjectForYandexAdsDemo' do
  use_frameworks!
end

target 'ProjectForYandexAds' do
  use_frameworks!
end

pod_targets_for_disable_build_for_distribution = [
  'VGSLBaseTiny-framework',
  'VGSL_Fundamentals_tiny',
  'VGSL_Fundamentals_Tiny-framework',
  'VGSLBase-framework',
  'VGSL_Fundamentals-framework',
  'DivKit_LayoutKit-library',
  'DivKit_LayoutKitInterface-framework',
  'DivKit_LayoutKitInterface-library'
]

post_install do |installer|
  installer.pods_project.targets.each do |target|
  
    if pod_targets_for_disable_build_for_distribution.include?(target.name)
      target.build_configurations.each do |config|
        config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'NO'
      end
    end
  end
  
  installer.generated_projects.each do |project|
    project.targets.each do |target|
      target.build_configurations.each do |config|
        config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = deployment_target
      end
    end
    
    project.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = deployment_target
    end
    
  end
end
