---
title: Lync Server 2013：前端伺服器 VoIP 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 762b7a43343e10fe4d6bec601954474ba3a44b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Lync Server 2013 的前端伺服器 VoIP 元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

前端伺服器上的 VoIP 元件如下：

  - 轉譯服務

  - 輸入路由元件

  - 輸出路由元件

  - Exchange UM 路由元件

  - Intercluster 路由元件

  - [Lync Server 2013 中的轉送伺服器元件](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>轉譯服務

「轉譯服務」是負責根據系統管理員定義的正規化規則，將撥打的號碼轉譯成 E.164 格式或其他格式的伺服器元件。如果您的組織使用私人編號系統或使用不支援 E.164 的閘道或 PBX，則「轉譯服務」可以轉譯為 E.164 以外的其他格式。

</div>

<div>

## <a name="inbound-routing-component"></a>輸入路由元件

輸入路由元件主要會根據使用者在其 Enterprise Voice 用戶端所指定的喜好設定來處理來電。 它也有助於代理人響鈴與同時響鈴 (若使用者已設定) 的使用。 例如，使用者可指定未應答的電話是否要轉接，還是只記錄下來進行通知。 如果已啟用來電轉接，使用者可以指定是否要將未應答的呼叫轉寄到另一個號碼，或是已設定為提供呼叫應答的 Exchange UM 伺服器。 預設會在所有 Standard Edition server 和前端伺服器上安裝傳入路由元件。

</div>

<div>

## <a name="outbound-routing-component"></a>輸出路由元件

輸出路由元件會將電話路由傳送到 PBX 或 PSTN 目的地。 它會對來電者套用使用者的語音原則所定義的電話授權規則，然後決定最適合用來路由每通電話的 PSTN 閘道。 預設會在所有 Standard Edition server 和前端伺服器上安裝輸出路由元件。

輸出路由元件所使用的路由邏輯會使用大的度量 (由網路或電話語音管理員根據其組織的需求而設定)。

</div>

<div>

## <a name="exchange-um-routing-component"></a>Exchange UM 路由元件

Exchange UM 路由元件會處理 Lync Server 與執行 Exchange 整合通訊 (UM) 之間的路由，以整合 Lync Server 與整合通訊功能。

Exchange UM 路由元件也會在 Exchange UM 伺服器無法使用時，處理透過 PSTN 的語音信箱重新路由。 如果您有在分支網站上的 Enterprise Voice 使用者，而該分支網站沒有指向中央網站的彈性 WAN 連結，您在分支網站上部署的 Survivable 分支裝置會在 WAN 中斷期間為分支使用者提供語音信箱留存能力。 當 WAN 連結無法使用時，Survivable 分支裝置會執行下列作業：

  - 透過 PSTN，將未接聽的電話重新路由至中央網站的 Exchange Unified Messaging 伺服器

  - 提供使用者透過 PSTN 擷取語音信箱訊息的能力

  - 將未接來電通知排入佇列，然後在 WAN 連結恢復時將通知上傳至 Exchange UM 伺服器。

為了啟用語音信箱重新路由，我們建議您的 Exchange 管理員設定 Exchange UM 自動語音應答 (AA) 僅接受郵件。

如需這些功能的詳細資訊，請參閱在 lync server [2013 中規劃 Exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)，以及[在 lync Server 2013 中規劃 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

</div>

<div>

## <a name="intercluster-routing-component"></a>Intercluster 路由元件

Intercluster 路由元件負責將電話路由至受話者的主要登錄器集區。如果該集區無法使用，此元件會轉而將電話路由至受話者的備份登錄器集區。如果無法透過 IP 網路聯繫到受話者的主要與備份登錄器集區，Intercluster 路由元件會透過 PSTN 將電話重新路由至使用者的電話號碼。

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端伺服器元件

位於前端伺服器或 Director 上的其他元件，可為 VoIP 提供必要的支援，但不是本身 VoIP 元件，包括下列各項：

  - **使用者服務。** 針對每一來電的目的地電話號碼執行反向號碼查閱，並將該號碼與目的地使用者的 SIP URI 相比對。 使用這項資訊，「輸入路由元件」就可將電話分支到該使用者的註冊 SIP 端點。 使用者服務是所有前端伺服器及 Director 上的核心元件。

  - **使用者複寫器。** 從 Active Directory 網域服務析取使用者電話號碼，並將它們寫入 RTC 資料庫中的表格，以供使用者服務和通訊錄服務器使用。 使用者複製器是所有前端伺服器上的核心元件。

  - **Address Book Server。** 將 Active Directory 網域服務的全域通訊清單資訊提供給 Lync Server 用戶端。 它也會從 RTC 資料庫中取得使用者和連絡人資訊，並將資訊寫入通訊錄檔案，然後將檔案儲存在 Lync 用戶端下載之共用資料夾上。 Address Book Server 會將資訊寫入 RTCAb 資料庫，而通訊錄 Web 查詢服務會使用該資訊，回應 Microsoft Lync 2010 Mobile 的使用者搜尋查詢。 它會選擇性地正常化要寫入 RTC 資料庫的企業使用者電話號碼，以在 Lync 中布建使用者連絡人的目的。 預設會在所有前端伺服器上安裝通訊錄服務。 預設會隨每一部前端伺服器上的 Web 服務安裝通訊錄 Web 查詢服務。

</div>

</div>

<span> </span>

</div>

</div>

</div>

