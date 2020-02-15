---
title: 'Lync Server 2013: Direct SIP 部署選項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4bbacbbb6f1a420e989f4bed02ba2fc0db6f85f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的直接 SIP 部署選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

本主題提供範例拓樸部署的直接 SIP 連線。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server 獨立

如果您的組織會使用其中一個這一節所述的部署，您可以使用唯一的電話語音解決方案 Lync Server 2013 的部分或全部的組織。 本節說明在詳細資料中的下列部署：

  - **漸進式部署：** 此選項假設您有現有的專用交換機 (pbx) 基礎結構，且您想要以較小的群組或組織內的團隊逐漸引進 Enterprise Voice。

  - **Lync Server 僅限 VoIP 部署：** 此選項假設您考慮部署 Enterprise Voice 在沒有傳統電話語音基礎結構的網站。

<div>

## <a name="incremental-deployment"></a>漸進式部署

在漸進式部署 Lync Server 2013 是唯一的電話語音解決方案的個別小組或部門，同時的其餘部分組織中的使用者繼續使用 PBX。 這個漸進式部署策略提供 IP 電話語音引入受控制的試驗程式透過企業的一種方法。 其通訊需求最佳由 Microsoft 整合通訊的工作群組移至 Enterprise Voice 時保持在現有的 PBX 上的其他使用者。 視需要額外的工作群組可移轉至 Enterprise Voice。

[增量] 選項如果，建議您清楚地定義使用者群組，已在通用和，通訊需求擔任集中管理。 此選項也是如果您有小組或部門的改變會展現透過寬的地理區域，可大幅節省的長途電話有效的。 事實上，這個選項適合用來建立其成員可能可能分佈在全球的虛擬小組。 您可以建立、 修改或 disband 這類 teams 快速回應移位業務需求。

下圖顯示部署企業語音 PBX 後方的一般拓撲。 這是漸進式部署的建議的拓撲。

**漸進式部署選項**

![部門的移轉選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門的移轉選項圖表")

<div>


> [!NOTE]  
> 如果您連線您的 Lync Server 部署到認證的直接 SIP 合作夥伴，就不需要中繼伺服器和 PBX 間的公用交換的電話網路 (PSTN) 閘道。 認證直接 SIP 協力廠商的清單，請參閱 Microsoft Unified Communications Open Interoperability Program 網站， <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>。



</div>

<div>


> [!NOTE]  
> 此圖所示的媒體路徑有媒體旁路啟用 （建議的組態）。 如果您選擇停用媒體旁路，媒體路徑會透過中繼伺服器路由傳送。



</div>

在此拓撲中，選取的部門或工作群組已啟用 Enterprise Voice。 PSTN 閘道連結 Voice over Internet Protocol (VoIP)-啟用工作群組]，將 PBX。 已啟用 Enterprise voice，包括遠端工作者，使用者透過 IP 網路通訊。 Enterprise Voice 使用者的來電至 PSTN 和同事未啟用 Enterprise voice 會路由到適當的 PSTN 閘道。 通話仍在 PBX 系統、 同事或來自 pstn，來電者會路由傳送至 PSTN 閘道，會進行路由轉送至 Lync 伺服器的呼叫。

有兩種建議的設定，以連線至現有的 PBX 基礎結構的互通性的企業語音： Enterprise Voice 在 PBX 前方的 Enterprise Voice 與 PBX 後方。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice 在 PBX 後方

Enterprise Voice 在 PBX 後方部署時，所有來自 PSTN 的通話都會送達 PBX，將企業語音使用者的通話路由傳送至 PSTN 閘道，並呼叫將 PBX 使用者至 PBX。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice 在 PBX 前方

Enterprise Voice 在 PBX 前方部署時，所有通話都會都送達 PSTN 閘道，哪些路由呼叫 Enterprise Voice 使用者 Lync 伺服器和 PBX 的 PBX 使用者的呼叫。 透過 IP 網路的成本最有效率的 PSTN 閘道路由傳送至 PSTN 的企業語音與 PBX 使用者的來電。 下表顯示這個設定的優缺點。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>部署 Enterprise Voice 在 PBX 前方的優點和缺點

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>優點</th>
<th>缺點</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX 仍然會服務未啟用 Enterprise Voice 的使用者。</p></td>
<td><p>現有的閘道可能不支援的功能或您想要的容量。</p></td>
</tr>
<tr class="even">
<td><p>PBX 可處理所有舊版的裝置。</p></td>
<td><p>需要閘道與 PBX 從和到中繼伺服器閘道在主幹。 您可能需要從服務提供者的多個主幹。</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice 使用者可保留相同的電話號碼。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server 僅限 VoIP 部署

Enterprise Voice 提供新的企業，以及新的 office 網站的現有的公司，而不必擔心 PBX 整合或產生大量的部署及維護實作的功能完整的 VoIP 解決方案IP PBX 基礎結構成本。 此解決方案支援同時對現場與遠端工作者。

在此部署中，所有的來電會透過 IP 網路路由傳送。 PSTN 來電會路由到適當的 PSTN 閘道。 Lync 2013 或 Lync Phone Edition 做為 softphone。 遠端呼叫控制是無法使用，並且不必要的因為有使用者控制項沒有 PBX 電話。 語音信箱和自動語音應答服務可透過指定部署的 Exchange 整合通訊 (UM)。

<div>


> [!NOTE]  
> 除了支援 Lync Server 2013 所需的網路基礎結構，僅限 VoIP 部署可以使用小型的合格閘道來支援傳真機和類比裝置。



</div>

下圖顯示在僅限 VoIP 部署的一般拓撲。

**僅限 VoIP 部署選項**

![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")

<div>


> [!NOTE]  
> 此圖所示的媒體路徑有媒體旁路啟用 （建議的組態）。 如果您選擇停用媒體旁路，媒體路徑會透過中繼伺服器路由傳送。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

