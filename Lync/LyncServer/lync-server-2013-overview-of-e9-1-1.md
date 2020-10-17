---
title: Lync Server 2013： E9-1-1 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1c97914abf8e5db393cd932c0a453885e86a5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530620"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 中的 E9-1-1 簡介

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Microsoft Lync Server 2013 支援 E9-1-1) 從 Lync 用戶端和 Lync Phone Edition 裝置呼叫的增強 9-1-1 (。 當您設定 Lync Server 的 E9-1-1 時，來自 Lync 2013 或 Lync Phone Edition 的緊急通話會包含緊急回應位置 (ERL) 位置資訊服務資料庫中的資訊。 Erl 是由市政 (所組成，也就是街道) 位址及其他資訊，可協助識別 office 大樓和其他多租戶設施中的更精確位置。 當使用者進行緊急通話時，Lync Server 會透過轉送伺服器將通話音訊路由傳送至 E9-1-1 服務提供者。 E9-1-1 服務提供者會使用來電者的市政位址，將通話路由傳送至公用安全回應點 (PSAP) 會提供給來電者的位置，並以緊急服務查詢金鑰 (ESQK 一起) 傳送，PSAP 用來查閱來電者的 ERL。

Lync Server 支援兩種方法，可將緊急通話路由傳送至 E9-1-1 服務提供者：

  - E9-1-1 服務提供者的會話初始通訊協定 (SIP) 主幹連接

  -  (PSTN) E9-1-1-1-1-1-1-1-1-1-1-1-1-1-1-1 服務提供者)  (

當您使用 SIP 主幹 E9-1-1 服務提供者時，會將 Erl 新增至位置資訊服務資料庫，然後依照主要街道位址指南 (MSAG) （由 E9-1-1 服務提供者所維護）來驗證位置。 如果 E9-1-1 服務提供者收到的來電沒有位置資訊，或其位置尚未針對 MSAG 驗證，請 E9-1-1 服務提供者會將通話路由傳送到國內/地區緊急通話回應中心 (ECRC) ，其專為訓練有素的人員，其口頭取得來電者的位置，並手動將通話路由到適當的 PSAP。  (某些 SIP 主幹 E9-1-1 服務提供者也會為客戶提供 PSTN direct 向內撥號 (是否) 號碼傳送至 ECRC，如果 SIP 主幹因任何原因而失敗，則會提供另一種路由9-1-1 呼叫的方式。 ) 

不同于時間分割多工 (TDM) 和 IP 型專用交換機 (PBX) 電話（具有固定位置），Lync 端點可以是非常行動的。 當您部署 E9-1-1 功能時，Lync Server 會協助確保無論來電者位於何處，緊急呼叫都可以路由傳送到叫用來電者位置的 PSAP。 例如，如果使用者的主辦公室位於 Redmond，但使用者在 Wichita 中從分公司的電腦撥打緊急電話，則 Kansas 會在 SIP 主幹或 PSTN 型 E9-1-1-1-1-1-1-1-1-1-1-1 服務提供者將通話路由傳送至 Wichita 中的 PSAP

當您使用 ELIN 閘道時，您也可以將 Erl 新增至位置資訊服務資料庫，但也包含每個位置的 ELIN 號碼。 ELIN 號碼會在緊急通話期間成為緊急電話號碼。 接著，您必須確定 PSTN 電信公司將 Elin 上傳至自動位置識別， (阿裡) 資料庫。

<div>


> [!NOTE]  
> Lync 連接的類比裝置無法從位置資訊服務接收位置資訊，或將位置資訊傳送至 E9-1-1 服務提供者。 如果您使用 SIP 主幹 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項： 
> <UL>
> <LI>
> <P><STRONG>傳統 PS-ALI 選項</STRONG> &nbsp; &nbsp; &nbsp;如果您在每個部署類比電話的網站上都有本機 PSTN 閘道，且每個類比電話都有，您可以直接布建類比裝置的位置，以專用交換機/自動位置識別 (PS-ALI) 服務提供者。 在此情況下，您可以設定巧盡心思構建的 Lync 語音原則，並將它們指派給類比裝置連絡人物件，使來自這些電話的 E9-1-1 呼叫直接路由傳送至 (服務提供者的 PSTN 提供者，而不是將通話路由傳送至 E9-1-1 服務提供者的 SIP 主幹) 。 當緊急通話時，與 PSTN 主幹相關聯之 PS-ALI 提供者的資料庫，會將每個類比電話的執行對應至實體位置，並提供此 PSAP 的位置。 這些記錄必須隨 PS-ALI 服務提供者一起更新，每次行動電話至不同的 Erl。</P>
> <LI>
> <P><STRONG>E9-1-1 服務提供者選項</STRONG> &nbsp; &nbsp; &nbsp;您可以使用 E9-1-1 服務提供者註冊類比電話 DIDs 及其對應的 Erl （如果 E9-1-1 服務提供者支援此功能）。 如果提供者接收到來自 Lync Server 的呼叫，但該呼叫不包含 PIDF-LO 資料，則提供者可以查看是否有資料庫與呼叫方的執行號碼相符。 透過使用從其資料庫中取得的 ERL，提供者可以自動將緊急通話路由傳送到正確的 PSAP，PSAP 將會收到類比裝置和 ESQK 一起記錄的執行，讓 dispatcher 能夠查閱來電者的位置。</P></LI></UL>如果您使用 ELIN 閘道選項，且需要支援類比電話的 E9-1-1，您可以直接使用 PS-ALI 服務提供者布建類比裝置的位置，如上述第一個選項所述。



</div>

從 Lync Server 的觀點來看，E9-1-1 程式可以分為兩個階段：

  - 階段1：取得位置

  - 階段2：將緊急通話路由傳送至 E9-1-1 服務提供者

本節說明這些階段的運作方式。

如果您計畫將基礎結構設定為自動偵測用戶端位置，您必須先決定要用來將來電者對應至位置的網路元素。 如需可能選項的詳細資訊，請參閱 [在 Lync Server 2013 中定義用來判斷位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中取得位置](lync-server-2013-acquiring-a-location.md)

  - [在 Lync Server 2013 中使用 SIP 主幹路由傳送 E9-1-1 通話](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 通話](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

