---
title: Lync Server 2013：規劃中央網站語音回復性
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
ms.openlocfilehash: fbeda869c078e6adfce18088545428170b356980
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>在 Lync Server 2013 中規劃中央網站語音回復性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-30_

企業越來越多地在全球各地分佈多個網站。 維護緊急服務、存取技術支援人員，以及在中央網站不在服務時執行重要業務工作的能力，對於任何企業語音復原方案而言都是必要的。 當中央網站變得無法使用時，必須符合下列條件：

  - 必須提供語音容錯移轉。

  - 通常在中央網站上使用前端池登錄的使用者，必須能夠使用備用的 [前端] 池進行註冊。 這可以透過建立多個 DNS SRV 記錄來完成，每個記錄都可解析為每個中心網站中的控制器池或前端池。 您可以調整 SRV 記錄的優先順序和權重，讓該中央網站所提供的使用者取得對應的控制器，並將前端池排在其他 SRV 記錄中。

  - 在其他網站的使用者撥打電話和寄件者必須重新路由至 PSTN。

本主題將說明安全的中心網站語音復原建議的解決方案。

<div>

## <a name="architecture-and-topology"></a>架構與拓撲

若要在中央網站規劃語音復原，必須先基本瞭解 Lync Server 2013 註冊機構在啟用語音容錯移轉時所扮演的中心角色。 Lync Server 註冊機構是一種伺服器角色，可啟用用戶端註冊和驗證並提供路由服務。 它與標準版伺服器、前端伺服器、控制器或 Survivable 分支裝置上的其他元件一起存放。 註冊機構池是由在前端池執行並位於相同網站的註冊機構服務所組成。 前端池必須是負載均衡的。 建議使用 DNS 負載平衡，但硬體負載平衡是可接受的。 Lync 用戶端透過下列探索機制來探索前端池：

1.  DNS SRV 記錄

2.  自動探索 Web 服務（Lync Server 2013 中的新功能）

3.  DHCP 選項120

在 Lync 用戶端連線到前端池之後，它會由負載平衡器導向至池中的一個前端伺服器。 接著，該前端伺服器會將用戶端重定向到池中的首選註冊機構。

針對企業語音啟用的每個使用者都會指派給特定的註冊機構池，這會成為該使用者的主要註冊機構池。 在特定的網站，幾百或上千個使用者通常會共用單一主要註冊機構池。 若要考慮針對中央網站資源（無論是目前狀態、會議或容錯移轉的中心網站），由任何分支網站使用者使用的方式，建議您考慮每個分支網站使用者，就像使用者是使用中央網站註冊的使用者。 分支網站使用者的數目目前沒有限制，包括向 Survivable 分支裝置註冊的使用者。

若要在中央網站發生故障時保證語音復原能力，主要註冊機構池必須有一個指定的備份註冊機構池位於另一個網站。 您可以使用 [拓撲產生器復原設定] 來設定備份。 假設在兩個網站之間有彈性的 WAN 連結，主要註冊機構池已不再可用的使用者會自動導向到備份註冊機構池。

下列步驟說明用戶端探索與註冊程式：

1.  用戶端透過 DNS SRV 記錄來探索 Lync Server。 在 Lync Server 2013 中，您可以設定 DNS SRV 記錄，將多個 FQDN 傳回給 DNS SRV 查詢。 例如，如果企業 Contoso 有三個中心網站（北美、歐洲和亞太地區），且每個中央網站都有一個控制器池，則 DNS SRV 記錄可以指向三個位置中的每一個控制器池 Fqdn。 只要有其中一個位置的控制器池可供使用，用戶端就可以連線到第一個躍點 Lync 伺服器。
    
    <div>
    

    > [!NOTE]  
    > 使用控制器池是選用的。 您可以改為使用前端池。

    
    </div>

2.  控制器池會通知 Lync 用戶端使用者的主要註冊機構池和備份註冊機構池。

3.  Lync 用戶端會先嘗試連線到使用者的主要註冊機構池。 如果有可用的主要註冊機構池，註冊機構就會接受註冊。 如果主要註冊機構池無法使用，Lync 用戶端會嘗試連線到 [備份註冊機構] 池。 如果備份註冊機構池可用，且已確定使用者的主要註冊機構池無法使用（在特定的容錯移轉間隔內檢測到缺少心跳），備份註冊機構池就會接受使用者的註冊。 在備份註冊機構檢測到主要註冊機構再次提供後，備份註冊機構池會將容錯移轉 Lync 用戶端重新導向至其主要池。

下圖顯示可保證中心網站復原的建議拓撲。 這兩個網站是透過彈性 WAN 連結來連接。 如果中央網站變得無法使用，指派給該文件庫的使用者會被導向至備份網站進行註冊。

**中央網站語音復原的建議拓撲**

![中央網站語音恢復能力的拓撲](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央網站語音恢復能力的拓撲")

</div>

<div>

## <a name="requirements-and-recommendations"></a>需求與建議

下列針對實施中心網站語音復原的需求和建議適用于大多陣列織：

  - 主要和備份註冊器池所駐留的網站應該由彈性 WAN 連結來連接。

  - 每個中央網站都必須包含由一或多位註冊機構組成的註冊機構池。

  - 每個註冊機構池都必須使用 DNS 負載平衡、硬體負載平衡或兩者同時進行負載平衡。 如需規劃負載平衡配置的詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

  - 每個使用者都必須使用 Lync Server 管理命令介面**move-csuser** Cmdlet 或 lync server [控制台] 指派給主要註冊機構池。

  - 主要註冊機構池必須有一個位於不同中央網站的單一備份註冊機構池。

  - 主要註冊機構池必須設定為容錯移轉至備份註冊機構池。 根據預設，主要註冊機構會設定為在300秒間隔後容錯移轉至備份註冊機構池。 您可以使用 Lync Server 2013 拓撲產生器來變更此間隔。

  - 如在規劃檔中的 [[在 Lync Server 2013 中設定容錯移轉路線](lync-server-2013-configuring-a-failover-route.md)] 主題中所述，設定容錯移轉路線。 設定路線時，請指定位於主要路由中指定之閘道以外的網站上的閘道。

  - 如果中央網站包含您的主要管理伺服器，而且網站可能會在較長的期限內關閉，您必須在備份網站上重新安裝管理工具;否則，您將無法變更任何管理設定。

</div>

<div>

## <a name="dependencies"></a>因素

Lync Server 依賴下列基礎結構和軟體元件，以確保語音復原：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>元件</strong></p></td>
<td><p><strong>多功能</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>解析伺服器伺服器與伺服器用戶端連線的 SRV 記錄及記錄</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 與 Exchange Web 服務（EWS）</p></td>
<td><p>連絡人儲存空間;行事歷數據</p></td>
</tr>
<tr class="even">
<td><p>Exchange 整合訊息與 Exchange Web 服務</p></td>
<td><p>通話記錄、語音信箱清單、語音信箱</p></td>
</tr>
<tr class="odd">
<td><p>DHCP 選項120</p></td>
<td><p>如果 DNS SRV 無法使用，用戶端會嘗試使用 DHCP 選項120來探索註冊機。 若要使用此功能，必須設定 DHCP 伺服器或啟用 Lync Server 2013 DHCP。 如需詳細資訊，請參閱<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013</a>區段的分支網站復原需求中的分支網站復原需求的硬體和軟體需求。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Survivable 語音功能

如果已實現前面的需求和建議，則 [備份註冊機構] 池會提供下列語音功能：

  - 呼出 PSTN 通話

  - 當電話服務提供者支援容錯移轉至備份網站的功能時，輸入 PSTN 通話

  - 在相同網站和兩個不同網站之間的使用者之間的企業通話

  - 基本呼叫處理，包括呼叫保留、檢索及轉移

  - 兩方立即訊息，以及在相同網站的使用者之間共用音訊與影片

  - 來電轉接、同時撥打端點、呼叫委派及小組通話服務，但僅限雙方都在相同的網站上設定呼叫委派或所有團隊成員的情況下。

  - 現有的電話和用戶端仍能正常運作。

  - 詳細通話記錄 (CDR)

  - 驗證與授權

根據設定的方式，下列語音功能可能會在主要中心網站不在服務時運作：

  - 語音信箱存放與檢索
    
    如果您想要讓 Exchange UM 在主要中央網站不在服務時可用，您必須執行下列其中一項操作：
    
      - 變更 DNS SRV 記錄，讓中央網站上的 Exchange UM 伺服器指向其他網站上的 [備份 Exchange UM 伺服器]。
    
      - 設定每個使用者的 Exchange UM 撥號計畫，以將 Exchange UM 伺服器同時納入中心網站和備份網站，但將備份 Exchange UM 伺服器指定為已停用。 如果主要網站無法使用，Exchange 管理員必須在備份網站將 Exchange UM 伺服器標示為 [已啟用]。
    
    如果上述方案都無法使用，則在中央網站無法使用的情況下，Exchange UM 將無法使用。

  - 所有類型的會議
    
    已容錯移轉至備份網站的使用者可以加入由召集人所建立或託管的會議，但無法在自己的主要池上建立或託管會議，但已不再提供該會議。 同樣地，其他人不能加入託管在受影響使用者的主要池中的會議。

當主要的中央網站不在服務時，下列語音功能無法運作：

  - 會議自動助理

  - 目前狀態與 DND 的路由

  - 更新來電轉接設定

  - 回應群組服務和通話駐留

  - 提供新的電話和用戶端

  - 通訊錄網頁搜尋

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃分支網站語音彈性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

