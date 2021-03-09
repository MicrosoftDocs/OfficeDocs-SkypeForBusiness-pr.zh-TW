---
title: 在 Microsoft Teams 中執行服務品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何在 Microsoft Teams 中為貴組織的服務品質與 QoS () 做好準備。
localization_priority: Normal
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
ms.openlocfilehash: c07e3e71d391123d34ae64ebf5806c090c29a29d
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558202"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft Teams 中 (QoS) 服務品質

Microsoft Teams 中的服務品質 (QoS) 可讓對網路延遲敏感的即時網路流量 (例如語音或視視資料流程) 在較不敏感的流量前面「排線」 (例如下載新 App，其中額外下載第二秒並不是大交易) 。 QoS 使用 Windows 群組原則物件和埠型存取控制清單來識別並標記即時資料流中所有的封包。 這可協助您的網路提供語音、影片和螢幕共用資料流程私人網路絡頻寬的一部分。

如果您支援一大群遇到本文所述之問題的使用者，您可能需要執行 QoS。 使用者少的小型企業可能不需要 QoS，但即使在那裡也應該有説明。

如果沒有某種形式的 QoS，您可能會在語音和視訊中看到下列品質問題：

- 抖動 – 以不同費率抵達的媒體封包，可能會導致通話中缺少文字或音節
- 封包遺失 – 封包被丟棄，這也可能降低語音品質且難以理解語音
- 延遲的往返時間 (RTT) – 媒體封包需要很長的時間到達目的地，這會造成交談中的雙方之間明顯延遲，並造成人員互相討論

若要解決這些問題，最不復雜的方法就是增加內部和網際網路上的資料連線大小。 由於這通常成本高，QoS 提供一種更有效地管理您擁有的資源的方式，而不是增加頻寬。 若要解決品質問題，建議您先使用 QoS，然後只在必要時新增頻寬。

若要讓 QoS 生效，您必須在整個組織中使用一致的 QoS 設定。 任何無法支援 QoS 優先順序的路徑部分，都會降低通話、影片和螢幕畫面分享的品質。 這包括將設定適用于所有的使用者電腦或裝置、網路交換器、路由器到網際網路，以及 Teams 服務。

_圖 1.組織網路與 Microsoft 365 或 Office 365 服務之間的關係_

![網路與服務之間關係的圖例](media/Qos-in-Teams-Image1.png "組織網路與 Microsoft 365 或 Office 365 服務之間的關係：內部部署網路和裝置會與互連網路連接，而互連網路會與 Microsoft 365 或 Office 365 雲端語音和音訊會議服務連接。")

## <a name="qos-implementation-checklist"></a>QoS 執行檢查清單

從高層級來說，執行下列操作以執行 QoS：

1. [請確定您的網路已準備就緒](#make-sure-your-network-is-ready)。

1. [選取 QoS 的實現方法](#select-a-qos-implementation-method)。

1. [選擇每種媒體類型的初始埠範圍](#choose-initial-port-ranges-for-each-media-type)。

1. 實施 QoS 設定：
   1. 在使用群組原則物件 (GPO) [設定用戶端裝置埠範圍和標記的用戶端](QoS-in-Teams-clients.md)。
   2. 在路由器 (查看製造商的檔) 或其他網路裝置。 這可能包括埠型存取控制清單 (ACL) 或直接定義 QoS 佇列和 DSCP 標記，或所有這些標記。

      > [!IMPORTANT]
      > 我們建議您使用用戶端來源埠以及「any」的來源和目的地 IP 位址來實施這些 QoS 策略。 這會在內部網路上同時發現傳入和傳出媒體流量。  

   3. [設定您想要如何處理 Teams 會議的媒體流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。

5. [分析 Teams 網路上流量](#validate-your-qos-implementation) ，以驗證您的 QoS 實現。

當您準備要執行 QoS 時，請記住下列指導方針：

- Microsoft 365 的最短路徑是最佳方式。
- 關閉埠只會導致品質降低。
- 我們不建議在兩者之間遇到任何障礙，例如代理。
- 限制躍點數目：
  - 用戶端到網路邊緣 – 3 到 5 個躍點
  - ISP 到 Microsoft 網路邊緣 – 3 個躍點
  - Microsoft 網路邊緣到最終目的地 – 不相關

有關防火牆埠的組程，請前往 [Office 365 URL 和 IP 範圍](office-365-urls-ip-address-ranges.md)。

## <a name="make-sure-your-network-is-ready"></a>確定您的網路已準備就緒

如果您考慮進行 QoS 的實現，您應該已經決定頻寬需求及其他 [網路需求](prepare-network.md)。
  
整個網路的流量塞塞將會大幅影響媒體質量。 頻寬不足會導致品質降低和使用者體驗不佳。 隨著 Teams 採用率及使用量增加，請使用[](use-call-analytics-to-troubleshoot-poor-call-quality.md)報告、每個使用者通話分析和通話品質儀表板[ (CQD) ](turning-on-and-using-call-quality-dashboard.md)來找出問題，然後使用 QoS 和選擇性頻寬新增功能進行調整。

### <a name="vpn-considerations"></a>VPN 考慮

QoS 只有在呼叫者之間的所有連結上執行時，才能如預期運作。 如果您在內部網路上使用 QoS，且使用者從遠端位置進行登錄，則只能在內部受管理的網路中排列優先順序。 雖然遠端位置可以實實虛擬私人網路 (VPN) 來接收受管理的連接，但 VPN 會內生增加封包負荷，並造成即時流量的延遲。 建議您避免在 VPN 上即時進行通訊流量。

在具有跨洲受管理連結的通用群組織中，我們強烈建議 QoS，因為這些連結的頻寬與 LAN 比較有限。

## <a name="introduction-to-qos-queues"></a>QoS 佇列簡介

若要提供 QoS，網路裝置必須擁有將流量分類的方法，而且必須能夠區別語音或視音訊與其他網路流量。

當網路流量進入路由器時，流量會進入佇列。 如果未進行 QoS 策略的設定檔，則只會有一個佇列，而且所有資料會視為優先順序相同的先入先出。 這表示語音 (對延遲非常敏感) 可能會卡在流量後面，而延遲幾毫秒不會是問題。

當您執行 QoS 時，您可以使用多種壅塞管理功能之一來定義多個佇列，例如 Cisco 的優先順序佇列和以類別為基礎的加權合理佇列[ (CBWFQ) ，](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)以及避免垵塞塞的功能，例如加權隨機早期偵測[ (WRED) 。](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_圖 2.QoS 佇列的範例_

![QoS 佇列和頻寬劃分的圖例](media/Qos-in-Teams-Image2.png "可用的總頻寬會分成多個佇列 ，音訊、視視及其他流量，這些佇列已指派不同的優先順序。")

簡單來說，QoS 會建立資料網路中虛擬的「共同作業通路」，讓某些類型的資料永遠不會或很少遇到延遲。 建立這些通路之後，您可以調整其相對大小，並更有效地管理您擁有的連接頻寬，同時仍為貴組織的使用者供應商務級體驗。

## <a name="select-a-qos-implementation-method"></a>選取 QoS 實現方法

您可以透過埠型標記，使用存取控制清單 (網路路由器上) ACL 來實施 QoS。 埠型標記是最可靠的方法，因為它適用于混合式 Windows、Mac 和 Linux 環境，而且最容易執行。 行動用戶端不提供使用 DSCP 值來標記流量的機制，因此他們需要這個方法。  

使用埠型標記時，您的網路路由器會檢查內送封包，如果封包是使用特定埠或埠範圍而到達，它會將其識別為特定媒體類型，並將它放在該類型的佇列中，將預定 [的 DSCP](https://tools.ietf.org/html/rfc2474) 標記新增到 IP 封包標頭，讓其他裝置可以識別其流量類型，並在其佇列中給予優先順序。

雖然埠型標記可跨平臺運作，但只會標記 WAN 邊緣的流量 (無法完全標記到用戶端電腦) 產生管理負荷。 請參閱路由器製造商提供的檔，以參閱如何執行這個方法的指示。

### <a name="insert-dscp-markers"></a>插入 DSCP 標記

您也可以使用群組原則物件 (GPO) 來引導用戶端裝置在 IP 封包標頭中插入 DSCP 標記，以將其識別為特定的流量類型 (例如語音) 。< 路由器和其他網路裝置可以進行配置，以識別這一點，並且將流量放在另一個優先順序較高的佇列中。

雖然此案例完全有效，但僅適用于加入網域的 Windows 用戶端。 任何未加入網域的 Windows 用戶端裝置都將不會啟用 DSCP 標記。 其他用戶端 ，例如執行 macOS 的用戶端，都有硬式編碼的標記，而且一定會標記流量。

在加號方面，透過 GPO 控制 DSCP 標記可確保所有加入網域的電腦都收到相同的設定，而且只有系統管理員可以管理這些設定。 可以使用 GPO 的用戶端會標記在原始裝置上，然後已配置的網路裝置可以使用 DSCP 程式碼來識別即時串流，並給予適當的優先順序。

### <a name="best-practice"></a>最佳做法

如果可以，建議您在路由器的端點和埠型 ACL 上結合 DSCP 標記。 使用 GPO 來吸引大多數的用戶端，以及使用埠型 DSCP 標記，可確保行動、Mac 和其他用戶端仍可獲得 QoS 處理 (至少部分) 。

DSCP 標記可以比對到郵寄戳記，以向郵遞工作者指出遞送的緊急性，以及如何以最佳方式排序以快速遞送。 一旦將網路安排為即時媒體資料流程的優先順序之後，遺失的封包和延遲的封包應該會大幅縮減。

一旦網路中所有裝置都使用相同的分類、標記和優先順序，只要變更指派給每種流量類型之佇列的埠範圍大小，就可減少或消除延遲、封包中斷和抖動。 從 Teams 的觀點來看，最重要的組組步驟是封包的分類和標記。 不過，若要讓端對端 QoS 成功，您也需要仔細對齊應用程式佈建與基礎網路組式。 一旦 QoS 完全實作，持續管理就是根據貴組織的需求和實際使用量調整指派給每種流量類型的埠範圍的問題。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>選擇每種媒體類型的初始埠範圍

無論 DSCP 標記是由用戶端或網路本身根據 ACL 設定指派，DSCP 值會告訴對應設定的網路要給予封包或串流什麼優先順序。 每個媒體工作負載會獲得自己的唯一 DSCP 值 (其他服務可能會允許工作負載共用 DSCP 標記、Teams 不) 以及每個媒體類型所使用的已定義和個別埠範圍。 其他環境可能有現有的 QoS 策略，可協助判斷網路工作負載的優先順序。

不同即時串流工作負載的埠範圍相對大小會設定該工作負載的可用頻寬總比例。 回到我們稍早的貼文類比：一封有「Air Mail」戳記的信件，可能在一小時內被帶到最近的機場，而標示為「大宗郵件」標記的小包裹可以等候一天，然後再一天在一系列卸貨車的陸地上旅行。

_建議的初始埠範圍_

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|18|保證式轉送 (AF21)|
||||||

當您使用這些設定時，請注意下列事項：

- 如果您打算在未來執行 ExpressRoute，但尚未執行 QoS，我們建議您遵循指引，讓從寄件者到接收者之間的 DSCP 值相同。

- 所有用戶端 ，包括行動用戶端和 Teams 裝置，都會使用這些埠範圍，並受您利用這些來源埠範圍所實施的任何 DSCP 政策影響。 唯一會繼續使用動態埠的用戶端是瀏覽器型用戶端， (參與者使用瀏覽器加入) 。

- 雖然 Mac 用戶端使用相同的埠範圍，但它也會針對音訊 (EF (和視) AF41 (使用硬) 。 這些值無法進行配置。

- 如果您之後需要調整埠範圍以改善使用者體驗，埠範圍不能重迭，而且應該彼此相鄰。

## <a name="migrate-qos-to-teams"></a>將 QoS 遷移到 Teams

如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，且目前正在部署中。 Teams、Teams 會尊重現有的組配置，並且會使用與商務用 Skype 用戶端相同的埠範圍和標記。 在大多數的情況下，不需要進行額外的組案。

> [!NOTE]
> 如果您透過群組原則使用應用程式名稱 QoS 標記，您必須Teams.exe做為應用程式名稱。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>使用 PowerShell 在 Windows 上的 Teams 中實施 QoS

**設定音訊的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**設定影片的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**設定 QoS 以共用**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>在 Teams 系統管理中心管理來源埠

在 Teams 中，應主動管理不同工作負載使用的 QoS 來源埠，並在必要時進行調整。 參照每個媒體類型之 [選擇](#choose-initial-port-ranges-for-each-media-type)初始埠範圍中的資料表，埠範圍可調整，但 DSCP 標記無法進行配置。 一旦執行這些設定，您可能會發現指定媒體類型需要更多或較少的埠。 [您應](use-call-analytics-to-troubleshoot-poor-call-quality.md) 使用每個使用者通話分析和通話品質儀表板 [ (CQD) ](turning-on-and-using-call-quality-dashboard.md) 來決定在 Teams 已實施後調整埠範圍，並定期視需要變更。

> [!NOTE]
> 如果您已經根據來源埠範圍和商務用 Skype Online 的 DSCP 標記設定 QoS，相同的設定會套用至 Teams，且不需要對地圖進行進一步的用戶端或網路變更，不過您可能必須設定 [Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 中所使用的範圍，以符合商務用 Skype Online 的設定。

如果您先前在內部部署商務用 Skype Server，您可能需要重新檢查 QoS 策略。 配合您驗證的埠範圍設定調整這些策略，為 Teams 提供高品質的使用者體驗。

## <a name="validate-your-qos-implementation"></a>驗證 QoS 的實現

若要讓 QoS 生效，GPO 所設定 DSCP 值必須位於通話的兩端。 透過分析 Teams 用戶端所產生的流量，您可以確認當 Teams 工作負載流量在網路中移動時，DSCP 值沒有變更或去除。

最好是在網路出口點捕獲流量。 您可以在切換器或路由器上使用埠鏡像來協助進行這項操作。

## <a name="implement-qos-for-other-devices"></a>針對其他裝置實施 QoS

請閱讀這些主題，瞭解如何針對 Intune、Surface、iOS、Android 和 Mac 執行 QoS

- [Surface Hub 2S 的 QoS](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub 的 QoS](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [iOS、Android 和 Mac 版 QoS](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>相關主題

- [影片：網路規劃](https://aka.ms/teams-networking)

- [針對 Microsoft Teams 準備組織的網路](prepare-network.md)

- [在 Teams 用戶端中實施 QoS](QoS-in-Teams-clients.md)
