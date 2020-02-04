---
title: Lync Server 2013：資料收集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 中的資料收集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在 Microsoft Lync Server 2013 通訊軟體中，您可以執行 Microsoft Lync Server 2013、規劃工具，而不需記錄現有和建議的 IP 位址及 Edge 伺服器的完整功能變數名稱（Fqdn），但是這樣做很難所以不會造成設定錯誤。 例如，如果在一段時間內需要共存，常見的錯誤是從您的 Lync Server 2013 Edge 部署的現有 Edge 部署重複使用 Fqdn。 您可以在試算表、表格或其他視覺形式中，將現有與提議的 IP 位址及 Fqdn 寫下，以協助避免在安裝期間發生設定問題。

<div>


> [!WARNING]  
> 如果您使用的是舊版的規劃工具，您可能已經使用工具來建立拓撲，以及匯出拓撲結構檔以供在拓撲產生器中使用，發佈您的拓撲。 已從規劃工具中移除匯出拓撲的功能。 我們強烈建議您使用舊版的規劃工具來建立 Lync Server 2013 的拓撲檔，並產生不預期的結果。



</div>

因此，建議的方法是使用下列資料收集範本（對應到您的邊緣拓撲），收集您需要在規劃工具中輸入的各種 FQDN 和 IP 位址。 透過記錄目前與建議的設定，您可以將值放在您生產環境的適當內容中。 而且，您會強行考慮如何設定共存與功能，例如簡單的 Url、檔案共用及負載平衡。

若要成功部署 Microsoft Lync Server 2013，您必須瞭解個別元件的互動與依賴性。 您可以從現有的網路和伺服器基礎結構中收集資料，並在這些區段中套用規劃指南，就能將 Lync Server 2013 Edge 伺服器元件整合到您的基礎結構中。

在[Lync Server 2013 選擇拓撲](lync-server-2013-choosing-a-topology.md)中引入，有三種主要的體系結構，有兩種變化，共五種可能的部署案例。 您的資料收集起點就是其中一種案例。 IP 位址、伺服器名稱和功能變數名稱是與相符的憑證、防火牆和 DNS 圖表相符的範例，詳細說明完整規劃方案所需的資訊。 規劃圖並填入您所需的憑證，DNS 和防火牆值在跨小組通訊中尤為重要，在這種情況下，管理憑證授權單位、防火牆設定和 DNS 由團隊以外的小組所管理規劃部署。 圖表會提供必要元件的相關資訊，這些元件可用於傳達這些需求以進行跨團隊共同作業。

所提供的圖表是特意通用的，但可讓您在跨團隊案例中的需求（在網路、防火牆、證書建立與管理、伺服器部署和伺服器管理是由不同的群組來處理。 在進行 Lync Server 的部署時，擁有網路、防火牆、埠和通訊協定、證書及伺服器的設定所需的詳細資料是非常重要的。

**Edge 伺服器與邊緣池**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**反向 Proxy**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**主管或主管池**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

