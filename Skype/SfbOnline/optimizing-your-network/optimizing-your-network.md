---
title: 最佳化您的網路
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 下列需求對於確保您為組織設定的所有線上功能商務用 Skype健康狀態和成功非常重要。 我們知道有些人很技術，這份檔是適合您的，但有些則不是。 如果您需要協助設定線上商務用 Skype，您應該閱讀這份檔，以熟悉您需要考慮的內容。 當您與 Microsoft FastTrack 中心、您的 Microsoft Services 和帳戶小組合作，或與 Microsoft 合作夥伴合作時，或與 Microsoft 合作夥伴合作時，也會提供一些可以討論的問題。
ms.openlocfilehash: 1c4af624a59e0606b3ee5f9c115ad61a65dffbd0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586021"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>優化您的網路以商務用 Skype Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

下列需求對於確保您為組織設定的所有線上功能商務用 Skype健康狀態和成功非常重要。 我們知道有些人很技術，這份檔是適合您的，但有些則不是。 如果您需要協助設定線上商務用 Skype，您應該閱讀這份檔，以熟悉您需要考慮的內容。 當您與 Microsoft FastTrack 中心、您的 Microsoft Services[和](https://fasttrack.microsoft.com/office)帳戶小組合作，或與 Microsoft 合作夥伴合作時，或與[Microsoft](https://partnercenter.microsoft.com/pcv/search)合作夥伴合作時，也會提供您一些可以討論的問題。

## <a name="a-quick-overview"></a>快速概觀

商務用 Skype可讓您與公司或世界各地的同事或商務合作夥伴聯繫。

使用 商務用 Skype，您可以：

- 使用 IM、語音或視音訊通話開始交談。

- 查看您的連絡人何時可在線上、會議或進行展示。

- 設定會議的產業強度安全性。

- 在線上廣播給大量觀眾。

- 在會議期間展示您的螢幕畫面，或將控制權授予其他人。

- 在商務用 Skype程式中Office聊天、通話或加入會議。按一下滑鼠即可。

## <a name="why-is-this-all-so-important"></a>為什麼這一切這麼重要？

即時媒體的品質 (IP 上) 音訊、視視及應用程式共用品質受到端對端網路連接品質的嚴重影響。 若要商務用 Skype線上媒體質量，請務必確定公司網路與線上媒體之間商務用 Skype連線。 最好的方法就是根據網路容量來設定內部網路和雲端連線，以容納所有連線的 商務用 Skype 流量。

您可以與[Microsoft](https://partnercenter.microsoft.com/pcv/search)合作夥伴合作，將各種 Microsoft 365 或 Office 365 應用程式 ，包括雲端中的 商務用 Skype Online 連線到您的網路，而 商務用 Skype 即時語音和視訊通訊功能則要求網路服務必須特別配置為支援這些 Microsoft 365 和 Office 365 即時工作負載。 這包括頻寬足以承載所需流量的網路，且能夠支援服務品質 (QoS) ，為使用者供應商務課程體驗。

除了此處的資訊，還有其他資源可協助您成功規劃及部署商務用 Skype線上服務和功能，並確保您的網路服務符合這些要求：

- [使用 ExpressRoute 的通話流程](call-flow-using-expressroute.md)

- [商務用 Skype Online 中的 ExpressRoute 與 QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [線上媒體質量與網路連線商務用 Skype](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>針對服務 (QoS) 服務品質商務用 Skype

在移商務用 Skype Online 之前，您應該先看看您的網路處理音訊、視視和共用會話流量的能力。 與其他Microsoft 365 Office 365服務一樣，Microsoft 也提供下載[商務用 Skype](https://www.microsoft.com/download/details.aspx?id=19011)頻寬計算機，用來判斷每個公司網站所需的網路流量。 您應該執行使用方式模型，包括建立即時通訊流量媒體流量模型，以及每個公司位置的 商務用 Skype 流量量、計算流量，以及分析流量如何影響整體網路。 完成之後，分析此資料應提供網路需要改善的位置建議，並建議佇列大小，以提供絕佳的使用者體驗。

商務用 Skype即時流量會對於封包遺失、延遲和抖動敏感，這些在塞塞網路中經常發生。 服務品質 (QoS) 也稱為服務類別 -也必須部署在受管理的外部 WAN、受管理的內部 LANs 和企業型 WiFi 網路上。 這可協助正確商務用 Skype即時流量的優先順序，例如音訊和視音訊，而超過本地網路和 WAN 的其他非即時流量，為使用者創造更好的體驗。

商務用 Skype音訊必須部署在 EF (快速轉轉 - DSCP 46) 佇列和 商務用 Skype 影片必須部署在 AF41 (保證轉轉 - DSCP 34) 佇列中。 即使對等和會議流量也是如此，無論 電話系統 Microsoft 365 或 Office 365 或其他電話功能是否部署。

雖然其他 IP 電話產品的 LAN 和 WAN 中可能已經有現有的 QoS 政策，商務用 Skype 讓使用者在使用服務時能夠行動，並且從位置移至不同位置。 因此，QoS 策略必須在 LAN、WAN 和無線網路上標示，以確保所有流量商務用 Skype管理網路優先處理。

若要協助調整您的網路大小，請下載 商務用 Skype[計算機](https://www.microsoft.com/download/details.aspx?id=19011)。

有關媒體質量和 QoS 的更多資訊，請參閱 商務用 Skype [Online 中的媒體質量和網路連線商務用 Skype。](media-quality-and-network-connectivity-performance.md)

有關設定及管理 QoS 的更多資訊，請參閱 [管理服務品質](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)。

## <a name="bypass-proxies-and-wan-optimization-devices"></a>忽略代理和 WAN 優化裝置

所有Microsoft 365或Office 365線上商務用 Skype加密，通常無法由 Proxy 裝置檢查。 基於這些原因，我們建議您忽略所有 Microsoft 365 和 Office 365 的 Proxy 裝置，定義為使用者與 URL 和 IP 位址範圍Office 365[的通訊](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 由於 Proxy 裝置可能會延遲即時商務用 Skype線上媒體流，我們強烈建議您至少忽略該流量的 Proxy 裝置。

Microsoft 建議排除Microsoft 365 Office 365使用 PAC 檔案傳送Microsoft 365 Office 365流量到防火牆的 URL。

以下是一些可協助的可用資源：

- [Microsoft 365比較Office 365比較基準與績效歷程記錄來調整或調整績效](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [適用于或移Microsoft 365的網路Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365Proxy Pac 產生器](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [使用 WAN 優化控制器或流量/檢查裝置Microsoft 365或Office 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [使用 ExpressRoute 路由Microsoft 365或Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>忽略雙加密

若要為使用者提供最佳的音訊和視音訊體驗，您必須實施解決方案，防止 商務用 Skype 媒體 (音訊和視) 穿過虛擬私人網路絡 (VPN) 管道。 所有商務用 Skype流量都是使用傳輸層安全性 (TLS) 加密，而媒體工作負載會使用安全即時通訊協定 (SRTP) 。 訊號會使用 TLS 加密，而媒體工作負載會以 SRTP 加密。 在 VPN 管道傳送此流量會額外增加一層加密，以及用戶端與 Microsoft 365 或 Office 365 之間的額外網路躍點，這兩者都可能會導致會話降級，因為這會增加抖動、封包遺失和延遲。

防止流量商務用 Skype VPN 管道的其中一個選項是分割管道。 若要執行分割-分流，客戶應諮詢其 VPN 廠商如何在其軟體中執行此操作的具體資料。

> [!NOTE]
> 這僅適用于商務用 Skype工作負載，不適用於其他Microsoft 365或Office 365服務。

其他資源：

- [啟用 Lync Media 以忽略 VPN Tunnel](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [更多有關直接存取、分割管道和強制管道](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [啟用直接存取](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>確保已開啟正確的埠和通訊協定

客戶必須確保服務或服務所需的 URL 和 IP 位址Microsoft 365 Office 365。 有關線上版的所有 IP 位址和 URL 的完整清單，請參閱商務用 Skype URL 和 IP 位址範圍Office 365 URL[和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。

商務用 Skype用戶端會使用各種埠和通訊協定。 商務用 Skype 會話的網路流量方向和流程會因互動類型 (對等與多方) 以及內容共用和語音/視像的使用而有所差異。 您必須檢查並開啟埠和通訊協定清單，並特別注意來源和目的地埠。 例如，音訊流量在用戶端只使用 20 個埠 (50000-50019 TCP/UDP) ，但目的地埠可能位於服務端 10K 埠範圍 (50000-59999 TCP/UDP) 的任何位置。 這也包括在防火牆上開啟 TCP 443 和 UDP 3478。

可能需要其他網路組組才能支援 商務用 Skype Online。


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>使用針對手機和裝置優化商務用 Skype

在即時媒體會話中，所有參與者使用的媒體裝置 ，例如耳機和網路相機，對整體音訊和視音訊品質有很大的影響。 品質較低的裝置或具有不正確裝置磁碟機的裝置，會降低音訊的整體音效品質，並降低視音訊的影像品質。 另一方面，經過認證的裝置或品質良好的裝置可協助消除回音、雜訊篩選、視像解析度並減少延遲。

手機和裝置對使用者的音訊和視音訊品質有極大的影響。 商務用 Skype認證計畫是「Lync 相容」計畫的演進，並驗證裝置是否符合 Microsoft 的音訊和視音訊標準。 Microsoft 已測試並認證許多 IP 電話、USB 音訊和視像裝置、電腦和會議室裝置。 您應該查看針對 商務用 Skype 優化的裝置清單，並努力提供不同的裝置，以滿足貴組織中使用者的各種需求和個人喜好設定。

請參閱下列內容，以進一步瞭解支援與認證裝置的資訊：  

- [取得商務用 Skype Online 的電話](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [手機和裝置商務用 Skype](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [個人周邊設備的解決方案目錄](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [符合 Microsoft Lync 資格的電話和裝置](../../SfbPartnerCertification/lync-cert/ip-phones.md)

使用者開會及使用音訊和視像裝置的環境及周圍區域是音訊和視音訊品質的另一大因素。 從吵雜環境通話的使用者會聽到回音、雜亂且不清楚的音訊。 在深色或低亮度環境中，使用者無法為視片產生明亮、清楚的影像品質。 在會議室設定中，麥克風和視像裝置的位置會直接影響參與者會收到的聲音和影像品質。

若要更清楚地瞭解使用者的音訊和視音訊體驗，請使用 商務用 Skype **App** 工具選項 音訊裝置或視像裝置，對使用中的裝置進行變更，並自訂其  >    >  設定。  您也可以按一下檢查通話品質來檢查通話 **的音訊品質**。 如果他們按一下 **[檢查通話品質**，然後可以報告測試通話的品質與問題。

![在用戶端中商務用 Skype音訊。](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>相關主題

[商務用 Skype Online 中的 ExpressRoute 與 QoS](expressroute-and-qos-in-skype-for-business-online.md)
