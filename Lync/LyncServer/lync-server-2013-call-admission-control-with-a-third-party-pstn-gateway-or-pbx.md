---
title: 協力廠商 PSTN 閘道或 PBX 的通話許可控制
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
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Lync Server 2013 中的協力廠商 PSTN 閘道或 PBX 的通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

本主題說明如何將呼叫許可控制（CAC）部署在中繼伺服器的閘道介面與協力廠商公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）之間的連結上。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC

在從中繼伺服器的閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上，可以部署 CAC。

**Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC**

![案例 1：中繼伺服器和 PSTN 閘道間的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "案例 1：中繼伺服器和 PSTN 閘道間的 CAC")

在這個範例中，在中繼伺服器和 PSTN 閘道之間會套用 CAC。 如果在網路網站1的 Lync 用戶端使用者要透過 Network Site 2 中的 PSTN 閘道撥 PSTN 通話，媒體會透過 WAN 連結來流動。 因此，每個 PSTN 會話都會執行兩個 CAC 檢查：

  - 在 Lync 用戶端應用程式與中繼伺服器之間

  - 在中繼伺服器與 PSTN 閘道之間

這適用于網路 Site 1 中的用戶端撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端應用程式的出局 PSTN 呼叫。

<div>


> [!NOTE]
> 確認 PSTN 閘道所屬的 IP 子網已設定並與網路 Site 2 相關聯。<BR>請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。<BR>如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Case 2：在中繼伺服器與含媒體端接點的協力廠商 PBX 之間使用 CAC

此設定類似于 Case 1。 在這兩種情況下，中繼伺服器會知道在 WAN 連結的另一端終止媒體的裝置，以及具有媒體端接點（MTP）之 PSTN 閘道或 PBX 的 IP 位址，都是在轉送伺服器上設定為下一個躍點。

**Case 2：在中繼伺服器與含 MTP 的協力廠商 PBX 之間使用的 CAC**

![案例 2：中繼伺服器和具有 MTP 之 PBX 間的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "案例 2：中繼伺服器和具有 MTP 之 PBX 間的 CAC")

在這個範例中，在中繼伺服器與 PBX/MTP 之間會套用 CAC。 如果網路網站1的 Lync 用戶端使用者是透過網路 Site 2 中的 PBX/MTP 來撥打 PSTN 電話，則媒體會透過 WAN 連結來流動。 因此，對於每個 PSTN 會話，都會執行兩個 CAC 檢查：

  - 在 Lync 用戶端應用程式與中繼伺服器之間

  - 在中繼伺服器與 PBX/MTP 之間

這適用于對網路 Site 1 中的用戶端進行撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端的出局 PSTN 呼叫。

<div>


> [!NOTE]
> 確認 MTP 所屬的 IP 子網已設定並與網路 Site 2 相關聯。<BR>請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。<BR>如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Case 3：在中繼伺服器與協力廠商 PBX 之間的 CAC （不含媒體終止點）

Case 3 與前兩個案例稍有不同。 如果在協力廠商 PBX 上沒有 MTP，那麼對於協力廠商 PBX 的傳出會話要求，中繼伺服器不知道媒體將在 PBX 邊界中終止的位置。 在這種情況下，媒體會直接在中繼伺服器與協力廠商端點裝置之間流動。

**Case 3：在中繼伺服器與沒有 MTP 的協力廠商 PBX 之間使用 CAC**

![案例 3：中繼伺服器和不具有 MTP 之 PBX 間的 CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "案例 3：中繼伺服器和不具有 MTP 之 PBX 間的 CAC")

在這個範例中，如果網路網站1的 Lync 用戶端使用者透過 PBX 撥打電話給使用者，則中繼伺服器只能在 proxy 腿（在 Lync 用戶端應用程式和中繼伺服器之間）執行 CAC 檢查。 因為在進行會話時，中繼伺服器沒有端點裝置的相關資訊，所以在通話建立之前，無法在 WAN 連結（在中繼伺服器與協力廠商端點之間）執行 CAC 檢查。 不過，在建立會話之後，中繼伺服器會針對主幹上使用的頻寬進行記帳。

針對源自協力廠商端點的呼叫，您可以在進行會話要求時，在中繼伺服器端的兩面執行 CAC 檢查時，提供該端點裝置的相關資訊。

<div>


> [!NOTE]
> 確認端點裝置所屬的 IP 子網已設定並與網路 Site 2 相關聯。<BR>請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。<BR>如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

