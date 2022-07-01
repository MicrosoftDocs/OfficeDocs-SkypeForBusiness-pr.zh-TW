---
title: 在 Microsoft Teams 中實作服務品質
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何在 Microsoft Teams 中準備貴組織的服務品質網路 (QoS) 。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564141"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft Teams 中實作服務品質 (QoS) 

Microsoft Teams 中的服務品質 (QoS) 可讓對網路延遲敏感的即時網路流量 (例如，語音或視訊串流) 在較不敏感 (像是下載新應用程式等較不敏感的流量前面「換行」，而下載的額外秒數並不大) 。 QoS 會使用 Windows 群組原則物件和埠型存取控制清單來識別並標記即時串流中的所有封包。 這可協助您的網路提供語音、視訊和螢幕共用串流專用部分的網路頻寬。

如果您支援一大群遇到本文所述問題之使用者，那麼您可能需要實作 QoS。 使用者較少的小型企業可能不需要 QoS，但即使有 QoS，也應該會很有説明。

如果沒有某種形式的 QoS，您可能會在語音和視訊中看到下列品質問題：

- 抖動 – 以不同速率送達媒體封包，可能會導致通話中的字詞或音節遺失
- 封包遺失 – 封包掉落，也可能會導致語音品質較低且難以理解語音
- RTT)  (延遲的往返時間 – 媒體封包花費很長的時間抵達目的地，導致交談中的兩方之間明顯延遲，並導致其他人互相交談

解決這些問題最不復雜的方法是增加內部和網際網路的資料連線大小。 由於這通常是成本禁止使用，因此 QoS 提供一種更有效管理您資源的方式，而不是新增頻寬。 若要解決品質問題，建議您先使用 QoS，然後只在必要時新增頻寬。

若要讓 QoS 生效，您必須在整個組織中套用一致的 QoS 設定。 路徑中任何無法支援 QoS 優先順序的部分，都可能會降低通話、視訊和螢幕共用的品質。 這包括將設定套用至所有使用者電腦或裝置、網路交換器、路由器到網際網路，以及 Teams 服務。

_圖 1.組織網路與 Microsoft 365 或Office 365服務之間的關係_

![網路與服務之間的關聯圖例。](media/Qos-in-Teams-Image1.png "組織網路與 Microsoft 365 或Office 365服務之間的關係：內部部署網路和裝置會與互連網路連線，這會與 Microsoft 365 或Office 365雲端語音和音訊會議服務連線。")

## <a name="qos-implementation-checklist"></a>QoS 實作檢查清單

在高階執行下列動作以實作 QoS：

1. [確定您的網路已準備就緒](#make-sure-your-network-is-ready)。

1. [選取 QoS 實作方法](#select-a-qos-implementation-method)。

1. [選擇每個媒體類型的初始埠範圍](#choose-initial-port-ranges-for-each-media-type)。

1. 實作 QoS 設定：
   1. 在使用 群組原則 Object (GPO) [設定用戶端裝置埠範圍和標記的用戶端](QoS-in-Teams-clients.md)上。
   2. 在路由器 (查看製造商的檔) 或其他網路裝置。 這可能包括埠型存取控制清單 (ACL) ，或直接定義 QoS 佇列和 DSCP 標記，或所有這些專案。

      > [!IMPORTANT]
      > 我們建議使用用戶端來源埠以及「任何」的來源和目的地 IP 位址來實作這些 QoS 原則。 這會同時掌握內部網路上的內送和外寄媒體流量。  

   3. [設定您要如何處理 Teams 會議的媒體流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。

5. 透過分析網路上的 Teams 流量來[驗證 QoS 實作](#validate-your-qos-implementation)。

當您準備實作 QoS 時，請記住下列指導方針：

- 這是 Microsoft 365 最短的路徑。
- 關閉埠只會導致品質降低。
- 不建議在兩者之間使用任何障礙，例如 Proxy。
- 限制躍點數目：
  - 用戶端到網路邊緣 – 3 到 5 個躍點
  - ISP 到 Microsoft 網路邊緣 – 3 個躍點
  - Microsoft 網路邊緣到最終目的地 – 不相關

如需設定防火牆埠的相關資訊，請移[至Office 365 URL 和 IP 範圍](office-365-urls-ip-address-ranges.md)。

## <a name="make-sure-your-network-is-ready"></a>確定您的網路已準備就緒

如果您考慮的是 QoS 實作，您應該已經決定您的頻寬需求及其他 [網路需求](prepare-network.md)。
  
網路上的流量𶐯塞會大幅影響媒體質量。 缺少頻寬會導致效能降低和使用者體驗不佳。 隨著 Teams 採用和使用量增加，請使用報告、 [個別使用者通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)和 [通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 來識別問題，然後使用 QoS 和選擇性頻寬新增來進行調整。

### <a name="vpn-considerations"></a>VPN 考慮

只有在來電者之間的所有連結上實作 QoS 時，QoS 才能如預期般運作。 如果您在內部網路上使用 QoS，且使用者是從遠端位置登入，您只能在內部受管理的網路中排列優先順序。 雖然遠端位置可以透過實作虛擬私人網路 (VPN) 來接收受管理的連線，但 VPN 固有的會增加封包的負荷，並在即時流量中造成延遲。 建議您避免透過 VPN 執行即時通訊流量。

在具有跨洲受管理連結的通用群組織中，我們強烈建議使用 QoS，因為這些連結的頻寬與 LAN 比較有限。

## <a name="introduction-to-qos-queues"></a>QoS 佇列簡介

若要提供 QoS，網路裝置必須具備將流量分類的方式，而且必須能夠區分語音或視訊與其他網路流量。

當網路流量進入路由器時，流量會進入佇列。 如果未設定 QoS 原則，則只會有一個佇列，且所有資料會被視為優先順序相同的初次入帳。 這表示語音流量 (對於延遲非常敏感，) 可能會卡在流量後面，而延遲幾毫秒則不會造成問題。

當您實作 QoS 時，您會使用數種壅塞式管理功能之一來定義多個佇列，例如 Cisco 的優先順序排程和 [以類別為基礎的加權評定會佇列 (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 和避免壅塞功能，例如 [加權隨機提早偵測 (WRED) ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)。

_圖 2.QoS 佇列範例_

![QoS 佇列和頻寬除法的圖例。](media/Qos-in-Teams-Image2.png "可用頻寬總計會分成多個已指派不同優先順序的佇列，包括音訊、視訊及其他流量。")

簡單的類似是，QoS 會在您的資料網路中建立虛擬的「共車模式」，因此某些類型的資料永遠不會或很少發生延遲。 當您建立那些連結之後，您可以調整他們的相對大小，並更有效率地管理您擁有的連線頻寬，同時仍可為貴組織的使用者供應商務級體驗。

## <a name="select-a-qos-implementation-method"></a>選取 QoS 實作方法

您可以使用網路路由器上的存取控制清單 (ACL) ，透過埠型標記來實作 QoS。 埠式標記是最可靠的方法，因為它適用于混合式 Windows、Mac 和 Linux 環境，而且最容易實作。 行動用戶端不提供使用 DSCP 值來標記流量的機制，因此需要使用此方法。  

使用埠式標記時，您網路的路由器會檢查內送封包，如果封包是使用特定埠或埠範圍傳送，則會將封包識別為特定媒體類型，並將其置於該類型的佇列中，將預先確定的 [DSCP](https://tools.ietf.org/html/rfc2474) 標記新增至 IP 封包標頭，讓其他裝置可以辨識其流量類型，並將它放在佇列中的優先順序。

雖然埠型標記可跨平臺運作，但只會標記 WAN 邊緣的流量 (並非所有路由至用戶端電腦) ，並建立管理負荷。 如需實作此方法的指示，請參閱路由器製造商所提供的檔。

### <a name="insert-dscp-markers"></a>插入 DSCP 標記

您也可以使用 群組原則 物件 (GPO) 來引導用戶端裝置在 IP 封包標題中插入 DSCP 標記，以識別其為特定類型的流量 (例如語音) ，以實作 QoS。 路由器和其他網路裝置可以設定為辨識此值，並將流量放在另一個優先順序較高的佇列中。

雖然此案例完全有效，但僅適用于加入網域的 Windows 用戶端。 任何不是加入網域的 Windows 用戶端的裝置都不會啟用 DSCP 標記。 其他用戶端，例如執行 macOS 的用戶端，具有硬式編碼標籤，且一律會標記流量。

此外，透過 GPO 控制 DSCP 標記可確保所有加入網域的電腦都會收到相同的設定，而且只有系統管理員可以管理這些設定。 可使用 GPO 的用戶端會在原始裝置上標記，然後設定的網路裝置可以辨識 DSCP 程式碼的即時串流，並提供適當的優先順序。

### <a name="best-practice"></a>最佳做法

我們建議盡可能在端點使用 DSCP 標記和路由器上的埠 ACL。 使用 GPO 來抓取大多數的用戶端，同時使用埠型 DSCP 標記可確保行動裝置、Mac 和其他用戶端仍可獲得 QoS 處理 (至少部分) 。

DSCP 標記可以貼上郵資戳記，表示郵遞人員的配送十分緊急，以及如何針對快速遞送進行排序。 將網路設定為優先于即時媒體串流之後，遺失的封包和延遲封包應該會大幅減少。

一旦網路中的所有裝置都使用相同的分類、標記和優先順序，只要變更指派給每個流量類型所用之佇列的埠範圍大小，就可以減少或消除延遲、放棄封包，以及抖動。 從 Teams 的觀點來看，最重要的組態步驟是封包的分類和標記。 不過，若要讓端對端 QoS 成功，您也需要仔細地將應用程式的設定與基礎網路設定對齊。 完整實作 QoS 後，持續管理是根據貴組織的需求和實際使用量，調整指派給每個流量類型的埠範圍的問題。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>針對每種媒體類型選擇初始埠範圍

無論 DSCP 標記是由用戶端指派，還是由網路本身根據 ACL 設定指派，DSCP 值都會告訴對應設定的網路提供封包或串流的優先順序。 每種媒體工作負載都會取得其專屬的 DSCP 值 (其他服務可能會允許工作負載共用 DSCP 標記、Teams 不會) ，以及每個媒體類型所使用的已定義和個別埠範圍。 其他環境可能有現有的 QoS 策略，這可協助您判斷網路工作負載的優先順序。

不同即時串流工作負載的埠範圍相對大小會設定專屬於該工作負載之可用頻寬總計的比例。 若要回到我們先前的郵政類比：帶有「Air Mail」戳記的信件可能會在一小時內移至最近的機場，而標示為「大宗郵件」標記的小包裹可以等候一天，然後再旅行一連串地道。

_建議的初始埠範圍_

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|18|保證式轉送 (AF21)|
||||||

當您使用這些設定時，請注意下列事項：

- 如果您計畫未來實作 ExpressRoute，但尚未實作 QoS，建議您遵循指引，讓從寄件者到接收者的 DSCP 值都一樣。

- 所有用戶端，包括行動用戶端和 Teams 裝置，都會使用這些埠範圍，並受到您實作使用這些來源埠範圍之 DSCP 原則的影響。 唯一會繼續使用動態埠的用戶端是瀏覽器型用戶端 (可讓參與者使用其瀏覽器) 加入會議的用戶端。

- 雖然 Mac 用戶端使用相同的埠範圍，但也針對音訊 (EF) 和視訊 (AF41) 使用硬式編碼值。 這些值無法設定。

- 如果您之後需要調整埠範圍以改善使用者體驗，埠範圍無法重迭且應彼此相鄰。

## <a name="migrate-qos-to-teams"></a>將 QoS 移轉到 Teams

如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，現在正在部署。 Teams、Teams 會尊重現有的設定，並且會使用與商務用 Skype用戶端相同的埠範圍和標記。 在大多數情況下，不需要額外的設定。

> [!NOTE]
> 如果您透過 群組原則 使用應用程式名稱 QoS 標記，則必須將 Teams.exe 新增為應用程式名稱。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>使用 PowerShell 在 Windows 上的 Teams 中實作 QoS

**設定音訊 QoS**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**設定視訊的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**設定用於共用的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>管理 Teams 系統管理中心的來源埠

在 Teams 中，應主動管理不同工作負載所使用的 QoS 來源埠，並視需要進行調整。 參照 [ [選擇每個媒體類型的初始埠範圍](#choose-initial-port-ranges-for-each-media-type)] 中的資料表，可調整埠範圍，但 DSCP 標記無法設定。 一旦您實作這些設定，您可能會發現特定媒體類型需要的埠有較多或較少。 [每個使用者的通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) 和 [通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 應該用於在 Teams 實作之後決定調整埠範圍，並根據需求變更而定期使用。

> [!NOTE]
> 如果您已經根據來源埠範圍和 商務用 Skype Online 的 DSCP 標記來設定 QoS，相同的設定將套用至 Teams，而且不需要進一步的用戶端或網路變更對應，但您可能必須[設定 Teams 中使用的範圍](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)，以符合 商務用 Skype Online 的設定。

如果您先前已部署商務用 Skype Server內部部署，您可能需要重新檢查 QoS 原則。 調整原則以符合您已驗證的埠範圍設定，為 Teams 提供優質的使用者體驗。

## <a name="validate-your-qos-implementation"></a>驗證 QoS 實作

若要讓 QoS 生效，GPO 所設定的 DSCP 值必須在通話的兩端顯示。 藉由分析 Teams 用戶端產生的流量，您可以確認當 Teams 工作負載流量透過網路移動時，DSCP 值沒有變更或去除。

最好是在網路出口點擷取流量。 您可以在開關或路由器上使用埠鏡像來協助解決此問題。

## <a name="implement-qos-for-other-devices"></a>實作其他裝置的 QoS

請閱讀這些主題，瞭解如何實作適用于 Intune、Surface、iOS、Android 和 Mac 的 QoS

- [適用于 Surface Hub 2S 的 QoS](/surface-hub/surface-hub-2s-manage-intune)

- [適用于 Surface Hub 的 QoS](/surface-hub/surface-hub-qos)

- [iOS、Android 和 Mac 版 QoS](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>相關主題

- [影片：網路規劃](https://aka.ms/teams-networking)

- [針對 Microsoft Teams 準備組織的網路](prepare-network.md)

- [在 Teams 用戶端中實作 QoS](QoS-in-Teams-clients.md)