---
title: Lync Server 2013：E9-1-1 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 中的 E9-1-1 概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Microsoft Lync Server 2013 支援從 Lync 用戶端和 Lync Phone Edition 裝置呼叫增強版9-1-1 （E9-1）。 當您設定 Lync Server for E9-1-1 時，從 Lync 2013 或 Lync Phone Edition 發出緊急通話，包括來自位置資訊服務資料庫的緊急回應位置（ERL）資訊。 ERLs 是由市政（也就是街道）位址及其他資訊所組成，這些資訊可協助您識別更精確的 office 辦公樓及其他具多租戶功能的位置。 當使用者進行緊急通話時，Lync Server 會透過轉送伺服器傳送呼叫音訊，以及位置與回呼資訊，並透過中繼伺服器傳送給 E9-1-1 服務提供者。 E9-1 服務提供者使用來電者的市政位址，將呼叫路由至提供來電者位置的公用安全應答點（PSAP），然後沿著 PSAP 用來查詢來電者 ERL 的緊急服務查詢鍵（ESQK）傳送通話。

Lync Server 支援兩種方法，可將緊急呼叫路由至 E9-1-1 服務提供者：

  - 與合格 E9-1-1 服務提供者的會話初始通訊協定（SIP）中繼連線

  - 將緊急位置識別號碼（ELIN）閘道移至公用交換電話（PSTN）的 E9-1-1 服務提供者

當您使用 SIP 幹線 E9-1 服務提供者時，您會將 ERLs 新增至位置資訊服務資料庫，然後根據 E9-1 服務提供者所維護的主要街道位址指南（MSAG）來驗證位置。 如果 E9-1-1 服務提供者收到的通話沒有位置資訊，或有未針對 MSAG 驗證的位置，E9-1-1 服務提供者會將呼叫路由至國內/地區緊急電話回應中心（ECRC），該人員是由經過專門訓練的人員所組成，verbally 取得來電者的位置，並將呼叫手動傳送給適當的 PSAP。 （部分 SIP 幹線 E9-1 服務提供者也會將 PSTN 直向內撥號（已）號碼提供給 ECRC，這會提供路由9-1-1 呼叫的替代方法，如果 SIP 幹線由於任何原因而失敗。）

與時間系分複用（TDM）和 IP 專用分支 exchange （PBX）電話（具有固定位置）不同，Lync 端點可以是非常行動。 當您部署 E9-1-1 功能時，Lync Server 有助於確保無論來電者位於何處，緊急通話都可以傳送給提供來電者位置的 PSAP。 例如，如果使用者的主要 office 位於華盛頓州的雷蒙德，但使用者是在 Wichita、堪薩斯、SIP 主幹或 PSTN E9-1-1 服務提供者將呼叫傳送給 Wichita 中的 PSAP，但使用者是從分支辦公室中的電腦撥打緊急電話。，而不是在雷德蒙的 PSAP。

當您使用 ELIN 閘道時，您也會將 ERLs 新增至位置資訊服務資料庫，但每個位置也包含一個 ELIN 號碼。 ELIN 號碼會在緊急通話期間變成緊急電話號碼。 接著，您必須確認 PSTN 載波會將 ELINs 上傳到自動位置識別（阿裡）資料庫。

<div>


> [!NOTE]  
> Lync 連線的模擬裝置無法從位置資訊服務接收位置資訊，或是從 E9-1-1 服務提供者傳送位置。 如果您使用 SIP 幹線 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項： 
> <UL>
> <LI>
> <P><STRONG>傳統 PS-阿裡選項</STRONG>&nbsp;&nbsp;&nbsp;如果您在每個部署類比手機且每個類比電話都有的位置都有本機 PSTN 閘道，您可以直接使用私人開關/自動位置識別（PS-阿裡）服務提供者來預配類比裝置的位置。 在這種情況下，您可以設定巧盡心思設計的 Lync 語音原則，並將它們指派給類比裝置連絡人物件，讓來自這些電話的 E9-1 呼叫直接透過本機閘道路由至服務網站的 PSTN 提供者（而不是路由呼叫 E9-1-1 服務提供者 SIP 主幹）。 當緊急通話進入時，PS-阿裡 provider 中與 PSTN 幹線相關的資料庫會將每個類比電話的執行對應到一個物理位置，並提供此位置至 PSAP。 每次將手機移至不同的 ERLs，就必須使用 PS-阿裡服務提供者來更新這些記錄。</P>
> <LI>
> <P><STRONG>E9-1-1 服務提供者選項</STRONG>&nbsp;&nbsp;&nbsp;您可以使用 E9-1-1 服務提供者（如果 E9-1-1 服務提供者支援）來登錄類比電話 DIDs 及其對應的 ERLs。 如果提供者從 Lync Server 接收不含 PIDF-LO 資料的呼叫，提供者可以查看呼叫方是否有相符的資料庫。 透過使用從其資料庫取得的 ERL，提供者可以自動將緊急呼叫路由至正確的 PSAP，而 PSAP 會收到類比裝置的功能，以及允許 dispatcher 查閱來電者位置的 ESQK 記錄。</P></LI></UL>如果您使用的是 ELIN 閘道選項，且需要從類比電話支援 E9-1-1，您可以直接使用 PS-阿裡服務提供者來設定類比裝置的位置，如上述第一個選項中所述。



</div>

從 Lync Server 的角度來看，E9-1-1 處理常式可以分為兩個階段：

  - 階段1：取得位置

  - 階段2：傳送緊急通話至 E9-1-1 服務提供者

本節說明這些階段的運作方式。

如果您打算將基礎結構設定為自動偵測用戶端位置，您必須先決定要用哪些網路元素將呼叫者對應到位置。 如需有關可能選項的詳細資訊，請參閱[定義用來判斷 Lync Server 2013 中的位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中擷取位置](lync-server-2013-acquiring-a-location.md)

  - [在 Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 來電](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 來電](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

