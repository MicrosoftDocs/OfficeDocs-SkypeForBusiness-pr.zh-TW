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
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516570"
---
# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 中的資料收集

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在 Microsoft Lync Server 2013 通訊軟體中，您可以執行 Microsoft Lync Server 2013、規劃工具，但不會將現有和擬議的 IP 位址及 Edge Server 的完整功能變數名稱記錄 (Fqdn) 中，但這樣做非常難，但不會造成設定錯誤。 例如，如果在一段時間內需要共存，則常見的錯誤是針對您的 Lync Server 2013 Edge 部署重用現有 Edge 部署中的 Fqdn。 將現有和擬議的 IP 位址和 Fqdn 記入試算表、表格或其他視覺表單中，可協助避免安裝時出現安裝問題。

<div>


> [!WARNING]  
> 如果您已使用舊版本的規劃工具，您可能已使用工具來建立拓撲，並匯出拓撲檔，以供拓撲產生器用來發行您的拓撲。 已從規劃工具中移除匯出拓撲的功能。 強烈建議您不要使用舊版本的規劃工具建立 Lync Server 2013 的拓撲檔，否則會產生意外的結果。



</div>

因此，建議的方法是使用下列對應至 Edge 拓撲的資料收集範本，以收集您需要在規劃工具中輸入的各種 FQDN 和 IP 位址。 透過記錄目前和擬議中的設定，您可以將值放在實際執行環境的適當內容中。 而且，您會被迫考慮如何設定共存和功能，例如簡易 URLs、檔案共用及負載平衡。

若要順利部署 Microsoft Lync Server 2013，您需要瞭解個別元件的互動和依賴性。 透過收集現有網路和伺服器基礎結構中的資料，並套用這些區段中的計畫指導方針，您可以將 Lync Server 2013 Edge Server 元件整合至您的基礎結構。

在 [Lync Server 2013 中選擇拓撲](lync-server-2013-choosing-a-topology.md)時所引進，有三個主要架構有兩個變化，共五種可能的部署案例。 其中一種案例將會是您的資料收集的起始點。 IP 位址、伺服器名稱和功能變數名稱是相符的憑證、防火牆和 DNS 圖表的範例，可詳述完整規劃解決方案所需的資訊。 圖表和填入您所需的憑證中，DNS 及防火牆值對於跨小組通訊尤其重要，在這種情況下，在跨小組通訊中管理憑證授權單位單位，防火牆設定和 DNS 是由計畫部署的小組以外的小組所管理。 這兩個圖表提供必要元件的資訊，這些元件可用於通告跨小組共同作業的需求。

所提供的圖表是特意通用的，但是允許所有相關資料的集合，這些資料對於跨小組案例中的需求通訊是必要的，在此案例中，網路、防火牆、憑證的建立和管理、伺服器部署和伺服器管理都是由不同的群組來處理。 在進行 Lync Server 的部署時，有必要的網路、防火牆、埠和通訊協定、憑證和伺服器設定的詳細資料，都是非常重要的。

**Edge Server 和 Edge 集區**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**反向 Proxy**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Director 或 Director 集區**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

