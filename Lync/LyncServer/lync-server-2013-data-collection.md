---
title: 'Lync Server 2013: Data collection'
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
ms.openlocfilehash: 025e31ada5ff08b27591ebf27aade875494c1614
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Lync Server 2013 中的資料收集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

在 Microsoft Lync Server 2013 通訊軟體，您可以執行 Microsoft Lync Server 2013 規劃工具沒有記載您現有和建議的 IP 位址和 Edge Server 的完整網域名稱 (Fqdn)，但很明顯地較難執行動作這不會導致組態錯誤。 例如，如果共存所需的一段時間，常見的錯誤是從現有 Edge 部署 Lync Server 2013 Edge 部署重複使用 Fqdn。 透過具有現有和建議的 IP 位址和 Fqdn 試算表、 表格或其他 visual 表單以撰寫向下，您協助防止在安裝期間安裝問題。

<div>


> [!WARNING]  
> 如果您已使用舊版的規劃工具，您可能是使用工具來建立您的拓撲和匯出拓撲文件中的使用中拓撲產生器來發行拓撲。 若要匯出之拓撲的功能已移除規劃工具。 使用舊版的規劃工具來建立拓撲文件以供 Lync Server 2013 強烈建議不要，並將會產生無法預期的結果。



</div>

因此，建議的方法是使用下列的資料收集範本，以對應至您的 Edge 拓撲，以收集各種 FQDN 和 IP 位址，您必須將輸入規劃工具。 所記載的目前和建議的組態，您可以為您的實際執行環境中適當的內容放置值。 和，強制您考慮如何設定共存和功能，例如簡單 Url、 檔案共用及負載平衡。

若要順利部署 Microsoft Lync Server 2013，您需要了解依賴個別元件與之間的互動。 藉由收集資料從您現有的網路和伺服器基礎結構，並套用以下各節中的規劃指引，您可以將 Lync Server 2013 Edge Server 元件整合到您的基礎結構。

引進中[選擇 [Lync Server 2013 中的拓撲](lync-server-2013-choosing-a-topology.md)，有兩個變化，五個可能的部署案例總計與三個主要架構。 這些案例的其中一個會收集您資料的起始點。 IP 位址、 伺服器名稱和網域名稱會與一致相符的憑證、 防火牆和 DNS 圖表詳細說明，完整的規劃解決方案所需的資訊的範例。 圖表和填寫您所需的憑證、 DNS 和防火牆值是特別重要跨小組通訊中由團隊以外的小組受管理的憑證授權單位、 防火牆設定資料庫和 DNS 管理，計劃部署。 圖表提供所需的元件，可用來進行通訊的跨小組共同作業這些需求的資訊。

提供的圖表是刻意通用的但是允許的集合，其中網路可能需要進行通訊的需求跨小組案例中的所有相關資料、 防火牆、 憑證建立和管理伺服器部署和伺服器管理是由不同的群組處理。 需要的網路、 防火牆、 連接埠和通訊協定、 憑證和伺服器組態的必要詳細資料時，重要的 Lync Server 部署正在進行中。

**Edge Server 及 Edge 集區**

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

