---
title: 移轉程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a955133dcadfc1966225b643467e5640c81d128
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移轉程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

Lync Server 2013 的建議和支援的移轉程序是以並排移轉。 本主題說明應使用並存移轉的原因，並包含共存測試的相關資訊。

<div>

## <a name="side-by-side-migration"></a>並存移轉

幾乎在每種移轉時，您都應該使用並存移轉路徑。 在並排顯示遷移中，您部署搭配 Lync Server 2013 旁相對應的伺服器是執行 Lync Server 2010，新的伺服器，並再將作業轉移到新的伺服器。 將回復到 Lync Server 2010 必要時，您必須僅回原始的伺服器移動作業。 請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。

</div>

<div>

## <a name="coexistence-testing"></a>共存測試

您已部署 Lync Server 2013 中同時使用 Lync Server 2010 之後，部署代表共存測試 Lync Server 2013 和 Lync Server 2010 的狀態。 在此狀態中，請務必測試並確定服務已啟動、每個網台都可以受系統管理，且用戶端可與目前及舊版使用者通訊。 移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。 一般而言，測試階段共存存在整個 Lync Server 2013 試驗測試。 舊版使用者移至 Lync Server 2013 的一段時間以確保該應用程式相容性和功能正常運作。 試驗測試之後，使用者和應用程式會移至 Lync Server 2013 的實際執行版本和舊版集區與 Lync Server 2010 的應用程式會停用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

