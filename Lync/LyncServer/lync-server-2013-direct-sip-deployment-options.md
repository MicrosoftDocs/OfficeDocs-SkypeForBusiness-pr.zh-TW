---
title: Lync Server 2013：直接 SIP 部署選項
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
ms.openlocfilehash: 7aaecb9bd7b5fc4f144236f83f85f9e1e192784f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529110"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的直接 SIP 部署選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題提供部署直接 SIP 連線的範例拓撲。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server Stand-Alone

如果您的組織使用本節所述的其中一個部署，您可以使用 Lync Server 2013 作為部分或所有組織的唯一電話語音解決方案。 本節詳細說明下列部署：

  - **漸進式部署：** 此選項假設您有現有的私人分公司 exchange (PBX) 基礎結構，而您想要將 Enterprise Voice 逐步引入組織中較小的群組或小組。

  - **Lync Server 僅限 VoIP 部署：** 此選項假設您考慮在沒有傳統電話語音基礎結構的網站上部署 Enterprise Voice。

<div>

## <a name="incremental-deployment"></a>漸進式部署

在漸進式部署中，Lync Server 2013 是個別小組或部門的唯一電話語音解決方案，而組織中的其他使用者仍會繼續使用 PBX。 這項增量部署策略提供一種方法，透過控制的試驗計畫，將 IP 電話語音引入您的企業。 Microsoft 整合通訊最適合使用其通訊的工作組會移至 Enterprise Voice，其他使用者仍會保留在現有的 PBX 上。 其他的工作組可以視需要遷移至 Enterprise Voice。

如果您明確定義的使用者群組具有共同的通訊需求，且其本身適用于集中式管理，則建議使用 [累加] 選項。 如果您擁有遍佈地理區域的團隊或部門，而且在長途計費中的節約成本可能很大，此選項也會有效。 實際上，此選項對於建立其成員可能分散在全球的虛擬小組非常有用。 您可以建立、修改或 disband 這類團隊，以快速回應轉向的業務需求。

下圖顯示在 PBX 背後部署 Enterprise Voice 的一般拓撲。 這是增量部署的建議拓撲。

**漸進式部署選項**

![部門遷移選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門遷移選項圖表")

<div>


> [!NOTE]  
> 如果您要將 Lync Server 部署連接至認可的 Direct SIP 夥伴，則不需要在轉送伺服器和 PBX 之間 (PSTN) 閘道。 如需認證直接 SIP 合作夥伴的清單，請參閱 Microsoft 整合通訊開啟互通性計畫網站，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> 。



</div>

<div>


> [!NOTE]  
> 在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。 如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。



</div>

在此拓撲中，會為企業語音啟用選取的部門或工作組。 PSTN 閘道會將 Voice over Internet Protocol (VoIP 已啟用) 的 workgroup 連結至 PBX。 已啟用 Enterprise Voice （包括遠端工作者）的使用者在 IP 網路之間進行通訊。 由 Enterprise Voice 使用者對 PSTN 及未啟用 Enterprise Voice 的同事進行呼叫會路由傳送至適當的 PSTN 閘道。 來自位於 PBX 系統或 PSTN 之來電者的同事的來電會路由傳送至 PSTN 閘道，而該閘道會將通話轉送至 Lync 伺服器進行路由傳送。

有兩個建議設定，可將 Enterprise Voice 連接至現有的 PBX 基礎結構，以進行互通性：在 PBX 前端和 Enterprise Voice 之後的 Enterprise voice。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 背後的 Enterprise Voice

當 Enterprise Voice 部署在 PBX 背後時，所有來自 PSTN 的呼叫都會到達 PBX，這會將呼叫傳送至 Enterprise Voice 使用者到 PSTN 閘道，並呼叫 PBX 使用者至 PBX。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 前端的 Enterprise Voice

當 Enterprise Voice 部署在 PBX 的前方時，所有呼叫都會到達 PSTN 閘道，這會將 Enterprise Voice 使用者的通話路由傳送至 Lync Server，並將 PBX 使用者叫用至 PBX。 從 Enterprise Voice 和 PBX 使用者呼叫 PSTN 會透過 IP 網路路由傳送至最具成本效益的 PSTN 閘道。 下表顯示此設定的優點和缺點。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>在 PBX 前面部署企業語音的優缺點

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
<td><p>PBX 仍可為未啟用 Enterprise Voice 的使用者提供服務。</p></td>
<td><p>現有的閘道可能不支援您想要的功能或容量。</p></td>
</tr>
<tr class="even">
<td><p>PBX 處理所有舊版裝置。</p></td>
<td><p>需要從閘道到 PBX 的主幹，以及從閘道到轉送伺服器。 您可能需要從服務提供者獲得更多主幹。</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice 使用者保留相同的電話號碼。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP-Only 部署

Enterprise Voice 可提供新的企業，以及現有公司的新 office 網站，並有機會實施功能齊全的 VoIP 解決方案，而不需要擔心 PBX 整合或產生 IP-PBX 基礎結構的實際部署及維護成本。 此解決方案同時支援現場和遠端工作者。

在此部署中，所有呼叫都會透過 IP 網路路由傳送。 PSTN 的來電會路由傳送至適當的 PSTN 閘道。 Lync 2013 或 Lync Phone Edition 是做為 softphone 的服務。 因為沒有 PBX 電話供使用者控制，所以遠端呼叫控制無法使用且不需要。 語音信箱和自動語音應答服務可透過選用 Exchange 整合通訊 (UM) 進行部署。

<div>


> [!NOTE]  
> 除了支援 Lync Server 2013 所需的網路結構之外，僅 VoIP 部署也可以使用小型的合格閘道來支援傳真機器和類比裝置。



</div>

下圖顯示僅限 VoIP 部署的一般拓撲。

**僅限 VoIP 部署選項**

![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")

<div>


> [!NOTE]  
> 在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。 如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

