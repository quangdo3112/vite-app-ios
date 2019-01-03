platform :ios, '10.0'
inhibit_all_warnings!
source 'https://github.com/CocoaPods/Specs.git'
require './vite_pod'

targetArray = ['Vite', 'Vite-official', 'Vite-test', 'Vite-enterprise']

targetArray.each do |t|
    target t do
        use_frameworks!

        #vite kit

        vite_community_git = 'https://github.com/vitelabs/vite-community-ios.git'
        vite_community_commit = 'b6e41081ac865386717083fc9522e00731c2060f'

        vite_business_git = 'https://github.com/vitelabs/vite-business-ios.git'
        vite_business_commit = 'b720ca05ce4c3976795889285de36514b0772304'

        if t == 'Vite-official'
            vite_pod 'ViteCommunity', :git => vite_community_git, :commit => vite_community_commit, :subspecs => ['Official']
            vite_pod 'ViteBusiness', :git => vite_business_git, :commit => vite_business_commit, :subspecs => ['Official']
        elsif t == 'Vite-test'
            vite_pod 'ViteCommunity', :git => vite_community_git, :commit => vite_community_commit, :subspecs => ['Test']
            vite_pod 'ViteBusiness', :git => vite_business_git, :commit => vite_business_commit, :subspecs => ['Test']
        elsif t == 'Vite-enterprise'
            vite_pod 'ViteCommunity', :git => vite_community_git, :commit => vite_community_commit, :subspecs => ['Enterprise']
            vite_pod 'ViteBusiness', :git => vite_business_git, :commit => vite_business_commit, :subspecs => ['Enterprise']
        else
            vite_pod 'ViteBusiness', :git => vite_business_git, :commit => vite_business_commit
        end

        vite_pod 'ViteUtils', :git => 'https://github.com/vitelabs/vite-utils-ios.git', :commit => '45d9439f98bd8187d3cf1e02f60637c53bba48bf'
        vite_pod 'ViteWallet', :git => 'https://github.com/vitelabs/vite-wallet-ios.git', :commit => 'fbb842cdf99e101fd9659016825739f63ccecc03'
        vite_pod 'Vite_HDWalletKit', '1.2.0'

        pod 'SnapKit', '~> 4.0.0'
        pod 'BigInt', '~> 3.0'
        pod 'R.swift', '5.0.0.alpha.3'
        pod 'JSONRPCKit', '~> 3.0.0'
        pod 'PromiseKit', '~> 6.0'
        pod 'APIKit'
        pod 'ObjectMapper'
        pod 'MBProgressHUD'
        pod 'KeychainSwift'
        pod 'Moya'
        pod 'MJRefresh'
        pod 'KMNavigationBarTransition'
        pod 'XCGLogger', '~> 6.1.0'
        pod 'pop', '~> 1.0'
        pod 'DACircularProgress', '2.3.1'
        pod 'Kingfisher', '~> 4.0'
        pod 'NYXImagesKit', '2.3'

        #request
        pod 'SwiftyJSON'

        #statistics
        pod 'BaiduMobStat'

        #UI Control
        pod 'ActionSheetPicker-3.0'
        pod 'MBProgressHUD'
        pod 'Toast-Swift', '~> 4.0.1'
        pod 'RazzleDazzle'
        pod 'CHIPageControl'

        #table static form
        pod 'Eureka', '~> 4.3.0'

        #RX
        pod 'RxSwift', '~> 4.0'
        pod 'RxCocoa'
        pod 'RxDataSources', '~> 3.0'
        pod 'NSObject+Rx'
        pod 'RxOptional'
        pod 'RxGesture'
        pod 'Then'
        pod 'Action'
        pod 'ReusableKit', '~> 2.1.0'
        pod 'ReactorKit'

        #code review
        pod 'SwiftLint'

        #crash
        pod 'Fabric'
        pod 'Crashlytics'

        pod 'MLeaksFinder', :configurations => ['Debug']

        pod 'FSPagerView'
        pod 'DNSPageView'

        if t == 'Vite'
            target 'ViteTests' do
                inherit! :search_paths
            end
        end

    end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        if ['RazzleDazzle', 'JSONRPCKit', 'APIKit'].include? target.name
            target.build_configurations.each do |config|
                config.build_settings['SWIFT_VERSION'] = '4.0'
            end
        end
    end
end
