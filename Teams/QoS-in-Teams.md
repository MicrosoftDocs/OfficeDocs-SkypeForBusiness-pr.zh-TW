---
title: 在 Microsoft 團隊中實現服務品質
author: lanachin
ms.author: v-lanac
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 瞭解如何在 Microsoft 團隊中針對服務品質（QoS）準備貴組織的網路。
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
ms.openlocfilehash: d0fb9a90a3528ed8d2d7f4d2f00843a9215e92a2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902418"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft 團隊中實現服務品質（QoS）

本文將協助您在 Microsoft 團隊中為貴組織的服務品質（QoS）準備好貴組織的網路。 如果您支援大量的使用者，且遇到下列任何問題，您可能需要實施 QoS。 只有少數使用者的小型企業可能不需要 QoS，但甚至應該有説明。

QoS 是一種允許即時網路流量（例如語音或視頻資料流程），它可讓您在不太敏感的通信量（例如下載新的應用程式，增加額外的下載，而不是大筆交易）的情況下，以網路延遲為保密。 QoS 會識別並標示即時資料流中的所有資料包（使用 Windows 群組原則物件，以及稱為埠的存取控制清單的路由功能，如以下所示），這可協助您的網路為網路頻寬的專用部分提供語音、影片和螢幕共用。

若沒有某種形式的 QoS，您可能會在語音和影片中看到下列品質問題：

- 抖動：以不同速度傳輸的媒體資料包，可能會導致通話中遺失文字或音節。
- 資料包遺失-丟棄的資料包，也可能會降低語音品質，並難以理解語音效果。
- 延遲的往返時間（RTT）-媒體資料包需要很長的時間才能到達其目的地，這樣就會在交談中的兩個參與方之間產生明顯的延遲，讓人們彼此交談。

解決這些問題最簡單的方法，就是在內部與網際網路之間增加資料連線的大小。 由於這通常是成本低的，因此 QoS 提供一種更有效率的方式來管理您所擁有的資源，而不是新增資源。 若要充分解決品質問題，您需要在整個實現中使用 QoS，然後只在絕對必要的位置新增連線。

為了讓 QoS 生效，您的組織中將會有一致的 QoS 設定，因為如果路徑不支援您的 QoS 優先順序，可能會降低通話、影片和螢幕共用的品質。 這包括將設定套用至所有使用者電腦或裝置、網路交換器、網際網路的路由器，以及小組線上服務。

_圖1。組織的網路與 Office 365 服務之間的關聯性_

![網路與服務之間的關聯性圖例](media/Qos-in-Teams-Image1.png "組織的網路與 Office 365 服務之間的關係：內部部署的網路和裝置會與互連網路連線，這又會與 Office 365 雲端語音和音訊會議服務連線。")

在大多數情況下，將企業連線到雲端的網路將是不受管理的網路，您無法可靠地設定 QoS 選項。 提供可解決端對端 QoS 的單一選項是[Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)，但我們仍建議您在內部部署網路上針對入站與出站流量執行 QoS。 這將會在整個部署和減輕 chokepoints 的同時，提高即時溝通工作負載的品質。

## <a name="verify-your-network-is-ready"></a>確認您的網路已就緒

如果您正在考慮 QoS 實現，您應該已經決定您的頻寬需求與其他[網路需求](prepare-network.md)。 
  
  網路上的流量堵塞會大大影響媒體質量。 缺乏頻寬會導致效能下降，以及不佳的使用者體驗。 隨著團隊採用和使用量的增加，您可以使用 [報告]、[[呼叫分析] 和 [通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)] 來找出問題，然後使用 QoS 及選擇性頻寬新增功能進行調整。

### <a name="vpn-considerations"></a>VPN 考慮

QoS 只會在針對呼叫者之間的所有連結所執行時正常運作。 如果您在內部網路上使用 QoS，且使用者從遠端位置登入，則您只能在內部、受管理的網路內進行優先順序設定。 雖然遠端位置可以透過實施虛擬私人網路（VPN）來接收受管理的連線，但 VPN 本身會增加資料包的負荷，並在即時流量中產生延遲。 我們建議您避免透過 VPN 執行即時通訊流量。

在有跨洲之受管理連結的通用群組織中，我們強烈建議使用 QoS，因為這些連結的頻寬會與局域網的比較受到限制。

## <a name="introduction-to-qos-queues"></a>QoS 佇列簡介

若要提供 QoS，網路裝置必須能夠將流量分類，而且必須能夠區別語音或影片與其他網路流量。

當網路流量進入路由器時，通信量會放入佇列中。 如果未設定 QoS 原則，則只有一個佇列，且所有資料都會以相同的優先順序先進行處理，即先完成。 這表示語音流量（對延遲非常敏感）可能會停滯通信量，而延遲幾個額外毫秒就不會發生問題。

當您實現 QoS 時，您會使用數個擁塞管理功能（例如 Cisco 的優先順序佇列和類別式加權公平佇列[CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)）和擁塞回避功能（例如加權隨機的預先偵測[WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)）來定義多個佇列。

_圖2。QoS 佇列的範例_

![QoS 佇列和頻寬劃分的圖例](media/Qos-in-Teams-Image2.png "可用的總頻寬在多個佇列中劃分，即音訊、影片和其他流量，這些都已獲指派不同的優先順序。")

簡單的類比是，QoS 會在您的資料網路中建立虛擬「carpool 車道」，讓某些類型的資料永不出現或很少遇到延遲。 建立這些車道之後，您就可以調整其相對大小，以及更有效率地管理您擁有的連線頻寬，同時還能為貴組織的使用者供應商業級的體驗。

## <a name="select-a-qos-implementation-method"></a>選取 QoS 實現方法

您可以在網路路由器上使用存取控制清單（Acl），透過埠標記來實現 QoS。 以埠為基礎的標記是最可靠的方法，因為它能在混合式 Windows、Mac 和 Linux 環境中運作，且最容易實現。 行動用戶端不會提供使用 DSCP 值來標示流量的機制，所以需要這個方法。  

使用這個方法，您的網路路由器會檢查傳入的資料包，如果資料包是使用特定的埠或埠範圍來接收，則會將它識別為特定媒體類型，並將它放在該類型的佇列中， [DSCP](https://tools.ietf.org/html/rfc2474)以便讓其他裝置辨識其流量類型，並在其佇列中賦予其優先順序。

雖然這可跨平臺使用，但它只會在 WAN edge （並非所有用戶端電腦的方式）標示流量，並產生管理負荷。 您應該參閱路由器製造商提供的檔，以取得實現此方法的指示。

* * *

您也可以使用群組原則物件（GPO）來實現 QoS，以直接在 IP 包頭中插入 DSCP 標記（例如，語音），將 DSCP 標記插入到 IP 資料包標頭中。 路由器和其他網路裝置可以設定為可辨識此情況，並將通信量放在個別、較高優先順序的佇列中。

雖然這種情況完全有效，但只有加入網域的 Windows 用戶端才能運作。 任何不是加入網域之 Windows 用戶端的裝置，都不會啟用 DSCP 標記。 用戶端（例如 Mac OS）有硬式編碼標籤，而且總是會標記流量。

在加號兩側，透過 GPO 控制 DSCP 標記，以確保所有加入網域的電腦都會收到相同的設定，而且只有系統管理員可以管理它們。 可使用 GPO 的用戶端會在原始裝置上進行標記，然後設定的網路裝置可以透過 DSCP 代碼辨識即時資料流，並提供適當的優先順序。

* * *

我們建議在路由器的端點和埠上使用 DSCP 標記組合（如果可能的話）。 使用群組原則物件來捕捉大部分的客戶，以及使用埠式 DSCP 標記，將確保行動、Mac 和其他用戶端仍能取得 QoS 治療（至少部分）。

DSCP 標記可以是 likened 到郵票，指出郵政工人是傳送的緊急程度，以及如何將其排序以進行快速傳送。 將您的網路設定為提供即時媒體資料流程的優先順序之後，遺失的資料包和後期資料包就應該會大大減少。

一旦網路中的所有裝置都使用相同的分類、標記及優先順序，就可以變更指派給每個流量類型所使用之佇列的埠範圍的大小，以減少或避免延遲、刪除資料包和抖動。 從 [小組] 的角度來看，最重要的配置步驟是 [分類] 和 [資料包]，但針對端對端 QoS 是成功的，您也必須小心地將應用程式的設定與基礎網路設定進行對齊。 當 QoS 完全實現之後，持續進行的管理就是根據貴組織的需求與實際用法調整指派給每個流量類型的埠範圍的問題。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>選擇每種媒體類型的初始埠範圍

[DSCP] 值會告知根據 ACL 設定，要提供資料包或資料流程的優先順序設定，哪個優先順序是由用戶端或網路本身指派的。 每個媒體工作負載都會取得自己的唯一 DSCP 值（其他服務可能允許工作負荷共用 DSCP 標記、團隊不存在），以及每個媒體類型所使用的已定義和不同的埠範圍。 其他環境可能已有一個現成的 QoS 戰略，這將協助您判斷網路工作負載的優先順序。

不同即時資料流工作負載的埠範圍相對大小，會設定專用於該工作負載的總可用頻寬比例。 若要回到我們先前的主要類比：使用「Air Mail」戳記的字母，可能會在一個小時內取得最接近的機場，而標示為「大量信箱」的小型封裝則可以在一天前，在一系列卡車上在飛機上出差前等候一天。

下表顯示所需的 DSCP 標記，以及團隊和 ExpressRoute 所使用的建議對應媒體埠範圍。 這些範圍可以作為良好的起點，適合無法確定要在自己的環境中使用的使用者。 若要深入瞭解，請閱讀[ExpressRoute QoS 需求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。

_建議的初始埠範圍_

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|滿|保證式轉送 (AF21)|
||||||

使用這些設定時，請注意下列事項：

- 如果您打算在未來實施 ExpressRoute，但尚未實現 QoS，我們建議您遵循指導方針，讓 [DSCP 值] 與 [寄件者] 的 DSCP 值相同。
- 所有用戶端（包括行動用戶端和團隊裝置）都將使用這些埠範圍，並會受到您使用這些來源埠範圍所執行的任何 DSCP 原則所影響。 只有以瀏覽器為基礎的用戶端（也就是那些讓參與者使用其瀏覽器加入會議的用戶端），才會繼續使用動態埠的用戶端。
- 雖然 Mac 用戶端使用相同的埠範圍，但它也會針對音訊（EF）和 video （AF41）使用硬編碼值。 這些值無法設定。
- 如果您稍後需要調整埠範圍來改善使用者體驗，則埠範圍可能不會重疊，且應該彼此相鄰。

## <a name="migrate-qos-to-teams"></a>將 QoS 遷移至團隊

如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，且現在正在部署團隊，則團隊會尊重現有的設定，並使用相同的埠範圍，並將其標記為商務用 Skype 用戶端。 在大多數情況下，不需要進行額外的配置。

> [!NOTE]
> 如果您是透過群組原則使用應用程式名稱 QoS 標記，您必須新增 share.exe 作為應用程式名稱。

## <a name="qos-implementation-steps"></a>QoS 執行步驟

在極高的層次上，執行 QoS 需要下列步驟：

1. [確認您的網路已就緒](#verify-your-network-is-ready)
2. [選取 QoS 實現方法](#select-a-qos-implementation-method)
3. [選擇每種媒體類型的初始埠範圍](#choose-initial-port-ranges-for-each-media-type)
4. 實施 QoS 設定：
   1. 在使用 GPO 來[設定用戶端裝置埠範圍及標記](QoS-in-Teams-clients.md)的用戶端上
   2. 在路由器上（請參閱製造商檔）或其他網路裝置。 這可能包含以埠為基礎的 Acl，或只定義 QoS 佇列和 DSCP 標記，或是它們的全部。

      > [!IMPORTANT]
      > 我們建議您使用用戶端來源埠以及來源和目的地 IP 位址 "any" 來實現這些 QoS 原則。 這會在內部網路上捕捉傳入和傳出媒體流量。  

   3. 在[團隊系統管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. 在網路上分析小組流量，以[驗證 QoS 實現](#validate-the-qos-implementation)。

當您準備好要實施 QoS 時，請牢記下列準則：

- 最短的 Office 365 路徑是最佳做法。
- 關閉埠只會導致品質下降。
- 不建議在其間的任何障礙（例如 proxy）。
- 限制跳躍數：
  - 用戶端到網路邊緣–3到5個躍點。
  - ISP 至 Microsoft 網路邊緣–3個躍點
  - Microsoft 網路 edge 至最終目的地（不相關）

如需設定防火牆埠的相關資訊，請移至[Office 365 url 與 IP 範圍](office-365-urls-ip-address-ranges.md)。

## <a name="managing-source-ports-in-the-teams-admin-center"></a>管理團隊系統管理中心的來源埠

在團隊中，不同工作負載所使用的 QoS 來源埠應該積極管理，並視需要調整。 參照表格在[每個媒體類型的 [初始埠範圍](#choose-initial-port-ranges-for-each-media-type)] 中，埠範圍都是可調整的，但 DSCP 標記無法進行設定。 一旦您實現這些設定之後，您可能會發現特定媒體類型需要多或較少的埠。 [[通話分析] 和 [通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)] 應該用於決定是否要在團隊實施之後調整埠範圍，以及定期視需要變更。

> [!NOTE]
> 如果您已經根據來源埠範圍及商務用 Skype Online 的 DSCP 標記來設定 QoS，則相同的設定會套用至小組，而且不需要對對應進行進一步的用戶端或網路變更，不過您可能必須[將在團隊系統管理中心使用的範圍](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)與商務用 Skype Online 所設定的範圍相符。

如果您先前已在內部部署部署商務用 Skype Server，您可能需要重新檢查您的 QoS 原則，並視需要調整，以符合您已驗證的埠範圍設定，為小組提供高品質的使用者體驗。

## <a name="validate-the-qos-implementation"></a>驗證 QoS 實施

為了讓 QoS 生效，群群組原則物件所設定的 DSCP 值必須存在於呼叫的兩端。 您可以透過分析團隊用戶端產生的流量，確認當團隊工作負載流量透過網路轉移時，DSCP 值不會變更或剝離。

最好的是，您可以在網路出口點捕獲流量。 您可以在交換器或路由器上使用埠鏡像來協助解決這個情況。

### <a name="use-network-monitor-to-verify-dscp-values"></a>使用網路監視器驗證 DSCP 值

網路監視器是您可以[從 Microsoft 下載](https://www.microsoft.com/download/4865)以分析網路流量的工具。

1. 在執行網路監視器的電腦上，連接到已針對埠鏡像設定的埠，並開始捕獲資料包。

2. 使用 [團隊用戶端] 撥打通話。 在掛斷通話之前，請確定已建立媒體。

3. 停止捕獲。

4. 在 [**顯示篩選**] 欄位中，使用撥打電話之電腦的來源 IP 位址，並透過定義 DSCP 值46（十六進位0x2E）做為搜尋準則來縮小篩選器，如下列範例所示：

    來源 = = "192.168.137.201" 和 IPv4. DifferentiatedServicesField = = 0x2E

    ![[顯示篩選] 對話方塊中的螢幕擷取畫面篩選器。](media/Qos-in-Teams-Image4.png "[網路監視器] 中的 [顯示篩選] 對話方塊，顯示要套用的篩選。")

5. 選取 **[** 套用] 以啟動篩選。

6. 在 [**框架摘要**] 視窗中，選取第一個 UDP 資料包。

7. 在 [**畫面詳細資料**] 視窗中，展開 [IPv4 清單] 專案，並記下以**DSCP**開頭之行結尾的值。

    ![顯示 [畫面詳細資料] 對話方塊中 DSCP 設定的螢幕擷取畫面。](media/Qos-in-Teams-Image5.png "[網路監視器] 中的 [框架詳細資料] 對話方塊，醒目提示 [DSCP 設定]。")

在這個範例中，DSCP 值會設定為46。 這是正確的，因為使用的來源埠是50019，這表示這是語音工作負載。

針對由 GPO 標記的每個工作負荷，重複進行驗證。

## <a name="more-information"></a>詳細資訊

[影片：網路規劃](https://aka.ms/teams-networking)

[針對 Microsoft Teams 準備組織的網路](prepare-network.md)

[ExpressRoute QoS 需求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
