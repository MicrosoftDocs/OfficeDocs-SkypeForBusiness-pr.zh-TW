---
title: Lync Server 2013：規劃中央網站語音恢復能力
description: Lync Server 2013：規劃中央網站語音恢復能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567379"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>在 Lync Server 2013 中規劃中央網站語音恢復能力

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-30_

越來越多的企業開始將網站散佈到全球各地。 維護緊急服務、存取服務台，以及在中央網站停止服務時執行重要商務工作的能力，對任何 Enterprise Voice 恢復解決方案都是必要的。 當中央網站無法使用時，必須符合下列條件：

  - 必須提供語音容錯移轉功能。

  - 一般在中央網站上使用前端集區註冊的使用者，必須能夠使用替代的前端集區註冊。 若要執行此動作，可以建立多個 DNS SRV 記錄，每個記錄會解析為每一個中央網站的 Director 集區或前端集區。 您可以調整 SRV 記錄的優先順序和權重，這樣該中央網站所提供的使用者就能在其他 SRV 記錄中取得對應的 Director 和前端集區。

  - 撥入其他網站或由其他網站撥出的使用者通話必須重新路由至 PSTN。

本主題說明保障中央網站語音恢復能力的建議解決方案。

<div>

## <a name="architecture-and-topology"></a>架構與拓撲

在中央網站規劃語音彈性功能時，需要有一個基本瞭解 Lync Server 2013 註冊機構在啟用語音容錯移轉時所扮演的中央角色。 Lync Server 註冊機構是一種伺服器角色，可讓用戶端註冊及驗證，並提供路由服務。 它與 Standard Edition server、前端伺服器、Director 或 Survivable 分支裝置上的其他元件一起存放。 註冊集區包含在前端集區上執行的註冊機構服務，且位於相同的網站。 前端集區必須進行負載平衡。 我們建議具備 DNS 平衡功能，不過如果只有硬體負載平衡也可接受。 Lync 用戶端會透過下列探索機制來探索前端集區：

1.  DNS SRV 記錄

2.  Lync Server 2013 中的自動探索 Web 服務 (新功能) 

3.  DHCP 選項 120

在 Lync 用戶端連線至前端集區之後，它會被負載平衡器導向至集區中的前端伺服器之一。 然後，該前端伺服器又會將用戶端重新導向至集區中的首選註冊機構。

每個針對 Enterprise Voice 啟用的使用者會指派給特定的註冊機構集區，這會變成該使用者的主要註冊集區。 在特定網站上，數百名或數千名使用者通常會共用單一主要登錄器集區。 為了針對任何一個分支網站裡倚賴中央網站以獲得顯示狀態、會議或容錯移轉功能的使用者，記錄其對中央網站資源的使用情況，建議您將每位分支網站使用者視為向中央網站註冊的使用者。 分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。

為了確保中央網站故障時的語音恢復能力，主要登錄器集區必須在另一個網站上設有一台指定的備份登錄器集區。 您可以使用拓撲產生器恢復設定來設定備份。 假設兩個網站之間存在可恢復的 WAN 連結，則已無法再使用主要登錄器集區的使用者會自動導向至備用登錄器集區。

下列步驟說明用戶端探索與註冊程序：

1.  用戶端透過 DNS SRV 記錄來探索 Lync Server。 在 Lync Server 2013 中，您可以設定 DNS SRV 記錄，以傳回 DNS SRV 查詢的一個以上 FQDN。 例如，如果 Contoso 企業擁有三個中央網站 (北美、歐洲與亞太地區) 並在每個中央網站擁有一個 Director 集區，DNS SRV 記錄可以分別指向這三個位置的個別 Director 集區 FQDN。 只要其中一個位置有 Director 集區可用，用戶端就可以連線至第一個躍點 Lync Server。
    
    <div>
    

    > [!NOTE]  
    > 使用 Director 集區是選用的。 可以改為使用前端集區。

    
    </div>

2.  Director 集區會通知 Lync 用戶端使用者的主要註冊集區和備份報名者集區。

3.  Lync 用戶端會先嘗試連接至使用者的主要註冊集區。 如果主要登錄器集區有回應，該登錄器就會接受註冊。 如果無法使用主要註冊集區，Lync 用戶端會嘗試連線至 [備份註冊機構] 集區。 如果備份登錄器集區有回應且判斷使用者的主要登錄器集區沒有回應時 (藉由偵測特定容錯移轉間隔是否有活動訊號)，備份登錄器集區會接受使用者註冊。 在備份註冊機構偵測到主要報名者再次可用之後，[備份註冊機集區] 會將容錯移轉 Lync 用戶端重新導向至其主要集區。

下圖說明確保中央網站恢復能力的建議拓撲。這兩個網站由可恢復的 WAN 連結串連起來。當中央網站沒有回應時，指派至該集區的使用者就會被導向至備份網站進行註冊。

**中央網站語音恢復能力的建議拓撲**

![中央網站語音恢復能力的拓撲](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央網站語音恢復能力的拓撲")

</div>

<div>

## <a name="requirements-and-recommendations"></a>需求和建議

以下為大多數組織在實作中央網站語音恢復能力時適用的需求與建議事項：

  - 主要與備份登錄器集區所屬網站必須由可恢復的 WAN 連結來串連。

  - 每個中央網站必須內含一個登錄器集區，且該集區必須包含一或多個登錄器。

  - 每個註冊機構集區都必須使用 DNS 負載平衡、硬體負載平衡或兩者兩者進行負載平衡。 如需規劃負載平衡設定的詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

  - 每個使用者都必須使用 Lync Server 管理命令介面 **get-csuser** Cmdlet 或 Lync server 控制台，指派給主要註冊集區。

  - 主要登錄器集區必須在其他中央網站設有一個備份登錄器集區。

  - 主要登錄器集區必須設為容錯移轉至備份登錄器集區。 主要登錄器集區預設會在故障超過 300 秒之後容錯移轉至備份登錄器集區。 您可以使用 Lync Server 2013 拓撲產生器來變更此間隔。

  - 如規劃檔中的「在[Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)」主題中所述，設定容錯移轉路由。 設定路由時，所指定的閘道必須與主要路由之指定閘道分屬不同網站。

  - 如果中央網站內含主要管理伺服器，且該網站短期內可能無法恢復服務，則您需要在備份網站重新安裝管理工具，否則您將無法變更任何管理設定。

</div>

<div>

## <a name="dependencies"></a>相依性

Lync Server 取決於下列基礎結構和軟體元件，以確保語音復原能力：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>元件</strong></p></td>
<td><p><strong>功能</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>負責解析 SRV 記錄與 A 記錄以因應伺服器對伺服器，及伺服器對用戶端的連線需求</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 與 Exchange Web 服務 (EWS)</p></td>
<td><p>連絡儲存裝置；行事曆資料</p></td>
</tr>
<tr class="even">
<td><p>Exchange 整合通訊與 Exchange Web 服務</p></td>
<td><p>通話記錄、語音信箱清單、語音信箱</p></td>
</tr>
<tr class="odd">
<td><p>DHCP 選項 120</p></td>
<td><p>如果無可用的 DNS SRV，用戶端會嘗試使用 DHCP 選項 120 來探索登錄器。 若要執行此作業，您必須設定 DHCP 伺服器，或是必須啟用 Lync Server 2013 DHCP。 如需詳細資訊，請參閱 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 區段之分支網站恢復性需求</a> 中 Branch-Site 恢復的硬體和軟體需求。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Survivable Voice 功能

如果先前的需求與建議都實作完畢，則備份登錄器集區會提供下列語音功能：

  - 撥出 PSTN 電話

  - 撥入 PSTN 電話，前提是電話語音服務提供者支援容錯移轉至備份網站的功能

  - 相同與不同的網站之間的使用者，皆可進行企業通話

  - 基本通話處理，包括通話保留、取回和轉接

  - 兩方立即訊息及相同網站的使用者之間共用音訊與視訊功能

  - 來電轉接、端點同時響鈴、通話委派與小組通話服務，但前提是同一個網站裡通話委派的雙方或所有小組成員都有這些設定。

  - 現有的電話與用戶端將繼續運作。

  - 詳細通話記錄 (CDR)

  - 驗證與授權

依據這些功能的設定方式，當主要中央網站無法提供服務時，以下語音功能不一定能夠發揮功用：

  - 語音信箱儲放與接聽
    
    如果您想在主要中央網站中斷服務時提供 Exchange UM 服務的話，必須執行下列其中一個步驟：
    
      - 變更 DNS SRV 記錄，以便中央網站的 Exchange UM 伺服器指向另一個網站的備份 Exchange UM 伺服器。
    
      - 將每一位使用者的 Exchange UM 撥號對應表設定為同時在中央網站和備份網站上包含 Exchange UM 伺服器，但將備份 Exchange UM 伺服器指定為停用。 若主網站無法使用，Exchange 系統管理員必須將備份網站上的 Exchange UM 伺服器標示為 [已啟用]。
    
    如果上述兩種方案都不可行，則當中央網站無法使用時，便無法使用 Exchange UM。

  - 所有會議類型
    
    已經容錯移轉至備份網站的使用者，可以加入由開放使用集區的召集人所建立或主控的會議，但是由於該使用者所屬的主要集區已經不再提供服務，因此無法自行建立或主控會議。同理，其他使用者無法加入由受影響使用者之主要集區所主控的會議。

下列語音功能在主要中央網站中斷服務時將無法運作：

  - 會議自動語音應答

  - 顯示狀態與 DND 基礎路由

  - 更新來電轉接設定

  - 回應群組服務和通話駐留

  - 佈建新電話與用戶端

  - 通訊錄 Web 搜尋

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃分支網站語音彈性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

