---
title: 使用協力廠商 PSTN 閘道或 PBX 的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7abd33af2dd2a7a5858fd8b888201b6471d0cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502810"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>使用協力廠商 PSTN 閘道或 PBX 的 Lync Server 2013 中的通話許可控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

本主題說明如何在轉送伺服器的閘道介面和協力廠商公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX) 之間的連結上，部署通話許可控制 (CAC) 的範例。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>案例1：轉送伺服器和 PSTN 閘道之間的 CAC

CAC 可以從轉送伺服器閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上部署。

**案例1：轉送伺服器和 PSTN 閘道之間的 CAC**

![案例1：轉送伺服器 PSTN 閘道之間的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "案例1：轉送伺服器 PSTN 閘道之間的 CAC")

在此範例中，轉送伺服器和 PSTN 閘道之間會套用 CAC。 如果網路 Site 1 上的 Lync 用戶端使用者透過網路 Site 2 中的 PSTN 閘道撥打 PSTN 電話，該媒體會透過 WAN 連結進行流量。 因此，每個 PSTN 會話會執行兩個 CAC 檢查：

  - Lync 用戶端應用程式與轉送伺服器之間

  - 轉送伺服器和 PSTN 閘道之間

這適用于網路 Site 1 中的用戶端傳入 PSTN 通話，以及來自網路 Site 1 中用戶端應用程式的撥出 PSTN 通話。

<div>


> [!NOTE]
> 確定 PSTN 閘道所屬的 IP 子網已經過設定，並與網路網站2相關聯。<BR>請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。<BR>如需詳細資訊，請參閱 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>案例2：轉送伺服器和具有媒體終止點之協力廠商 PBX 之間的 CAC

這種設定與案例1類似。 在這兩種情況下，轉送伺服器都知道在 WAN 連結的相對端終止媒體的方式，以及 PSTN 閘道或 PBX 的 IP 位址，以及具有媒體終止點 (MTP) 會在轉送伺服器上設定為下一個躍點。

**案例2：轉送伺服器和具有 MTP 之協力廠商 PBX 之間的 CAC**

![案例2：轉送伺服器 PBX 與 MTP 之間的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "案例2：轉送伺服器 PBX 與 MTP 之間的 CAC")

在此範例中，轉送伺服器和 PBX/MTP 之間會套用 CAC。 如果網路網站1上的 Lync 用戶端使用者透過位於網路 Site 2 的 PBX/MTP 來撥打 PSTN 電話，該媒體會透過 WAN 連結進行流量。 因此，每個 PSTN 會話都會執行兩個 CAC 檢查：

  - Lync 用戶端應用程式與轉送伺服器之間

  - 轉送伺服器和 PBX/MTP 之間

這適用于對網路 Site 1 中的用戶端進行傳入 PSTN 通話，以及發自來自網路 Site 1 之用戶端的傳出 PSTN 通話。

<div>


> [!NOTE]
> 確定 MTP 所屬的 IP 子網已經過設定，並與網路網站2相關聯。<BR>請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。<BR>如需詳細資訊，請參閱 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>案例3：轉送伺服器和不具有媒體終端點之協力廠商 PBX 之間的 CAC

Case 3 與前兩個案例稍有不同。 如果在協力廠商 PBX 上沒有 MTP，轉送伺服器不會知道媒體在 PBX 界限中將終止的哪個位置。 在此情況下，媒體會直接流過轉送伺服器和協力廠商端點裝置。

**案例3：轉送伺服器和不具有 MTP 之協力廠商 PBX 之間的 CAC**

![案例3：轉送伺服器 PBX 之間的 CAC 無 MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "案例3：轉送伺服器 PBX 之間的 CAC 無 MTP")

在此範例中，如果網路 Site 1 上的 Lync 用戶端使用者透過 PBX 呼叫使用者，則轉送伺服器只能在 Lync 用戶端應用程式與轉送伺服器) 之間的 proxy 腿 (執行 CAC 檢查。 因為在要求會話時，轉送伺服器沒有端點裝置的相關資訊，所以在建立通話之前，無法在轉送伺服器和協力廠商) 端點之間的 WAN 連結 (上執行 CAC 檢查。 在建立會話後，轉送伺服器會為主幹使用的頻寬進行會計核算。

針對來自協力廠商端點的呼叫，在會話要求時可使用該端點裝置的相關資訊，同時也可以在轉送伺服器的兩側執行 CAC 檢查。

<div>


> [!NOTE]
> 確定端點裝置所屬的 IP 子網已經過設定，並與網路網站2相關聯。<BR>請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。<BR>如需詳細資訊，請參閱 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

