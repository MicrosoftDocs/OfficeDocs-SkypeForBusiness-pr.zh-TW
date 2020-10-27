---
title: 在 Microsoft 團隊中實現服務品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何準備貴組織的網路，以瞭解 Microsoft 團隊中的服務品質 (QoS) 。
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
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766576"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft 團隊中實現服務品質 (QoS) 

Microsoft 團隊中的服務品質 (QoS) 可讓您對網路延遲造成機密的即時網路流量 (例如，語音或影片資料流程) 為「在其他位置換行」，而不是像是下載新的應用程式，而要下載的額外秒數則不是大型交易 (。 QoS 會使用 Windows 群組原則物件和埠式存取控制清單來識別並標示即時資料流中的所有資料包。 這可協助您的網路提供語音、影片和螢幕共用來串流網絡頻寬的專用部分。

如果您支援有大量的使用者遇到本文所述的任何問題，您可能需要實施 QoS。 只有少數使用者的小型企業可能不需要 QoS，但甚至應該有説明。

若沒有某種形式的 QoS，您可能會在語音和影片中看到下列品質問題：

- 抖動：以不同速度傳入的媒體資料包，可能會導致通話中遺失文字或音節
- 資料包遺失-丟棄的資料包，也可能導致語音品質降低且難以理解語音
- 延遲的往返時間 (RTT) -媒體資料包需要很長的時間才能到達其目的地，這會導致交談中的兩個參與方產生明顯的延遲，並讓其他人互相交談

解決這些問題最簡單的方法，就是在內部與網際網路之間增加資料連線的大小。 由於這通常是成本低的，因此 QoS 提供一種更有效率的方式來管理您所擁有的資源，而不是增加頻寬。 若要解決品質問題，建議您先使用 QoS，然後在必要時新增頻寬。

為了讓 QoS 生效，您必須在整個組織中套用一致的 QoS 設定。 路徑中無法支援 QoS 優先順序的任何部分，都可能會降低通話、影片和螢幕共用的品質。 這包括將設定套用至所有使用者電腦或裝置、網路交換器、網際網路的路由器，以及團隊服務。

_圖1。組織的網路與 Microsoft 365 或 Office 365 服務之間的關聯性_

![網路與服務之間的關聯性圖例](media/Qos-in-Teams-Image1.png "組織的網路與 Microsoft 365 或 Office 365 服務之間的關係：內部部署的網路和裝置會連線至互聯網絡，而這項功能又與 Microsoft 365 或 Office 365 雲端語音和音訊會議服務連線。")

## <a name="qos-implementation-checklist"></a>QoS 實施檢查清單

在高層中，請執行下列動作來實施 QoS：

1. [請確定您的網路已就緒](#make-sure-your-network-is-ready)

1. [選取 QoS 實現方法](#select-a-qos-implementation-method)

1. [選擇每種媒體類型的初始埠範圍](#choose-initial-port-ranges-for-each-media-type)

1. 實施 QoS 設定：
   1. 在使用群組原則物件的用戶端 (GPO) [設定用戶端裝置埠範圍和標記](QoS-in-Teams-clients.md)
   2. 在路由器上 (請參閱製造商說明文件) 或其他網路裝置。 這可能包含 (Acl 的埠式存取控制清單) 或只是定義 QoS 佇列和 DSCP 標記，或是它們的全部。

      > [!IMPORTANT]
      > 我們建議您使用用戶端來源埠以及來源和目的地 IP 位址 "any" 來實現這些 QoS 原則。 這會在內部網路上捕捉傳入和傳出媒體流量。  

   3. [設定您想要處理團隊會議媒體流量的方式](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. 分析網路上的小組流量，以[驗證您的 QoS 實現](#validate-your-qos-implementation)。

當您準備好要實施 QoS 時，請牢記下列準則：

- 最短的 Microsoft 365 路徑是最佳做法
- 關閉埠只會導致品質下降
- 不建議在任何情況下（例如 proxy）中的任何障礙
- 限制跳躍數：
  - 用戶端到網路邊緣–3到5個躍點
  - ISP 至 Microsoft 網路邊緣–3個躍點
  - Microsoft 網路 edge 至最終目的地（不相關）

如需設定防火牆埠的相關資訊，請移至 [Office 365 url 與 IP 範圍](office-365-urls-ip-address-ranges.md)。

## <a name="make-sure-your-network-is-ready"></a>請確定您的網路已就緒

如果您正在考慮執行 QoS，您應該已經決定您的頻寬需求與其他 [網路需求](prepare-network.md)。
  
網路上的流量堵塞會大大影響媒體質量。 缺乏頻寬會導致效能下降，以及不佳的使用者體驗。 隨著團隊採用和使用量的增加，您可以使用 [報告]、[ [每使用者通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)] 和 [ [通話品質儀表板] (CQD) ](turning-on-and-using-call-quality-dashboard.md) 來找出問題，然後使用 QoS 及選擇性頻寬增加進行調整。

### <a name="vpn-considerations"></a>VPN 考慮

QoS 只會在針對呼叫者之間的所有連結所執行時正常運作。 如果您在內部網路上使用 QoS，且使用者從遠端位置登入，則您只能在內部、受管理的網路內進行優先順序設定。 雖然遠端位置可以透過將虛擬私人網路絡 (VPN) 來接收受管理的連線，但 VPN 本身會增加資料包的負荷，並在即時流量中產生延遲。 我們建議您避免透過 VPN 執行即時通訊流量。

在有跨洲之受管理連結的通用群組織中，我們強烈建議使用 QoS，因為這些連結的頻寬會與局域網的比較受到限制。

## <a name="introduction-to-qos-queues"></a>QoS 佇列簡介

若要提供 QoS，網路裝置必須能夠將流量分類，而且必須能夠區別語音或影片與其他網路流量。

當網路流量進入路由器時，通信量會放入佇列中。 如果未設定 QoS 原則，則只有一個佇列，且所有資料都會以相同的優先順序先進行處理，即先完成。 這表示語音流量 (對延遲而言非常敏感，) 可能會停滯通信量，而延遲幾個額外的毫秒不會發生問題。

當您實現 QoS 時，您可以使用數個擁塞管理功能（例如 Cisco 的優先順序佇列和 [類別式加權公平佇列 ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) ）中的其中一個來定義多個佇列， (CBWFQ) 與擁塞規避功能，例如 [加權隨機 WRED， () ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)。

_圖2。QoS 佇列的範例_

![QoS 佇列和頻寬劃分的圖例](media/Qos-in-Teams-Image2.png "可用的總頻寬在多個佇列中劃分，即音訊、影片和其他流量，這些都已獲指派不同的優先順序。")

簡單的類比是，QoS 會在您的資料網路中建立虛擬「carpool 車道」，讓某些類型的資料永不出現或很少遇到延遲。 建立這些車道之後，您就可以調整其相對大小，以及更有效率地管理您擁有的連線頻寬，同時還能為貴組織的使用者供應商業級的體驗。

## <a name="select-a-qos-implementation-method"></a>選取 QoS 實現方法

您可以透過以埠為基礎的標記來實現 QoS，使用網路路由器上 (Acl) 的 [存取控制清單]。 以埠為基礎的標記是最可靠的方法，因為它能在混合式 Windows、Mac 和 Linux 環境中運作，且最容易實現。 行動用戶端不會提供使用 DSCP 值來標示流量的機制，所以需要使用這個方法。  

使用以埠為基礎的標記，您的網路路由器會檢查傳入的資料包，如果資料包是使用特定的埠或埠範圍來接收，則會將它識別為特定的媒體類型，並將它放在該類型的[DSCP](https://tools.ietf.org/html/rfc2474)佇列中，以便讓其他裝置辨識其流量類型，並在其佇列中賦予其優先順序。

雖然以埠為基礎的標記可跨平臺使用，但它只會在 WAN edge 中標示流量， (並不完全在用戶端電腦) 並產生管理額外負荷。 請參閱路由器製造商提供的檔，以取得實現此方法的指示。

### <a name="insert-dscp-markers"></a>插入 DSCP 標記

您也可以使用群組原則物件來實現 QoS， (GPO) 將用戶端裝置插入 IP 包頭中，以將 DSCP 標記插入到特定類型的通訊 (例如，語音) 。 路由器和其他網路裝置可以設定為可辨識此情況，並將通信量放在個別、較高優先順序的佇列中。

雖然這種情況完全有效，但只有加入網域的 Windows 用戶端才能運作。 任何不是加入網域之 Windows 用戶端的裝置，都不會啟用 DSCP 標記。 用戶端（例如 Mac OS）有硬式編碼標籤，而且總是會標記流量。

在加號兩側，透過 GPO 控制 DSCP 標記，以確保所有加入網域的電腦都會收到相同的設定，而且只有系統管理員可以管理它們。 可使用 GPO 的用戶端會在原始裝置上進行標記，然後設定的網路裝置可以透過 DSCP 代碼辨識即時資料流，並提供適當的優先順序。

### <a name="best-practice"></a>最佳做法

我們建議在路由器的端點和埠上使用 DSCP 標記組合（如果可能的話）。 使用 GPO 來捕捉大部分的客戶，以及使用埠式的 DSCP 標記，可確保行動裝置、Mac 和其他用戶端仍能取得 QoS 治療 (至少部分) 。

DSCP 標記可以是 likened 到郵票，指出郵政工人是傳送的緊急程度，以及如何將其排序以進行快速傳送。 將您的網路設定為提供即時媒體資料流程的優先順序之後，遺失的資料包和後期資料包就應該會大大減少。

一旦網路中的所有裝置都使用相同的分類、標記及優先順序，就可以變更指派給每個流量類型所使用之佇列的埠範圍的大小，以減少或避免延遲、刪除資料包和抖動。 從 [小組] 的角度來看，最重要的 [設定] 步驟是 [分類] 與 [資料包] 的標記。 不過，若要成功進行端對端 QoS，您也必須小心地將應用程式的設定與基礎網路設定對齊。 當 QoS 完全實現之後，持續進行的管理就是根據貴組織的需求與實際用法調整指派給每個流量類型的埠範圍的問題。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>選擇每種媒體類型的初始埠範圍

[DSCP] 值會告知根據 ACL 設定，要提供資料包或資料流程的優先順序設定，哪個優先順序是由用戶端或網路本身指派的。 每個媒體工作負載都會取得自己獨特的 DSCP 值 (其他服務可能允許工作負荷共用 DSCP 標記、團隊不) ，以及每個媒體類型所使用的已定義及不同埠範圍。 其他環境可能已有一個現成的 QoS 戰略，這將協助您判斷網路工作負載的優先順序。

不同即時資料流工作負載的埠範圍相對大小，會設定專用於該工作負載的總可用頻寬比例。 若要回到我們先前的主要類比：使用「Air Mail」戳記的字母，可能會在一個小時內取得最接近的機場，而標示為「大量信箱」的小型封裝則可以在一天前，在一系列卡車上在飛機上出差前等候一天。

_建議的初始埠範圍_

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|滿|保證式轉送 (AF21)|
||||||

使用這些設定時，請注意下列事項：

- 如果您打算在未來實施 ExpressRoute，但尚未實現 QoS，我們建議您遵循指導方針，讓 [DSCP 值] 與 [寄件者] 的 DSCP 值相同。
- 所有用戶端（包括行動用戶端和團隊裝置）都將使用這些埠範圍，並會受到您使用這些來源埠範圍所執行的任何 DSCP 原則所影響。 只有以瀏覽器為基礎的用戶端， (的用戶端，讓參與者使用其瀏覽器加入會議) 。
- 雖然 Mac 用戶端使用相同的埠範圍，但它也會針對 (EF) 與 video (AF41) 使用硬式編碼值。 這些值無法進行設定。
- 如果您稍後需要調整埠範圍來改善使用者體驗，則埠範圍不能重疊，且應該彼此相鄰。

## <a name="migrate-qos-to-teams"></a>將 QoS 遷移至團隊

如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，且現在正在部署。 團隊、團隊會尊重現有的設定，並使用相同的埠範圍，並將其標記為商務用 Skype 用戶端。 在大多數情況下，不需要進行額外的配置。

> [!NOTE]
> 如果您是透過群組原則使用應用程式名稱 QoS 標記，您必須將 Teams.exe 新增為應用程式名稱。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>使用 PowerShell 在 Windows 上的小組中實施 QoS

**設定音訊的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**設定視頻的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**設定 QoS 以進行共用**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>管理團隊系統管理中心的來源埠

在團隊中，不同工作負載所使用的 QoS 來源埠應該積極管理，並視需要調整。 參照表格在 [每個媒體類型的 [初始埠範圍](#choose-initial-port-ranges-for-each-media-type)] 中，埠範圍都可調整，但 DSCP 標記無法進行設定。 一旦您實現這些設定之後，您可能會發現特定媒體類型需要多或較少的埠。 [[每使用者通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)] 和 [[通話品質儀表板] (CQD) ](turning-on-and-using-call-quality-dashboard.md)應該用來決定在團隊實施之後調整埠範圍，以及定期視需要變更。

> [!NOTE]
> 如果您已經針對商務用 Skype Online 的來源埠範圍和 DSCP 標記設定了 QoS，則相同的設定會套用至小組，而且不需要進一步的用戶端或網路變更，不過您可能必須 [將小組中所用的範圍](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 與針對商務用 Skype Online 所設定的範圍相符。

如果您先前已部署商務用 Skype Server 內部部署，您可能需要重新檢查您的 QoS 原則。 調整原則以符合您所驗證的埠範圍設定，為小組提供高品質的使用者體驗。

## <a name="validate-your-qos-implementation"></a>驗證您的 QoS 實施

為了讓 QoS 生效，GPO 設定的 DSCP 值必須存在於呼叫的兩端。 您可以透過分析團隊用戶端產生的流量，在小組工作負載流量透過網路移動時，確認 DSCP 值沒有變更或剝離。

最好的是，您可以在網路出口點捕獲流量。 您可以在交換器或路由器上使用埠鏡像來協助解決這個情況。

## <a name="implement-qos-for-other-devices"></a>針對其他裝置實施 QoS

請閱讀下列主題，以取得有關針對 Intune、Surface、iOS、Android 和 Mac 實施 QoS 的詳細資訊

- [Surface Hub 的 QoS 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub 的 QoS](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [IOS、Android 和 Mac 版 QoS](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>相關主題

- [影片：網路規劃](https://aka.ms/teams-networking)

- [針對 Microsoft Teams 準備組織的網路](prepare-network.md)

- [在團隊用戶端中實施 QoS](QoS-in-Teams-clients.md)
