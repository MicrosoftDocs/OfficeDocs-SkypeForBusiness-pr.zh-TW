---
title: 移轉程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>移轉程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

Lync Server 2013 的建議和支援的遷移程式是並行遷移程式。 本主題描述為什麼您應該使用並列移植，同時還包含有關共存的資訊。

<div>

## <a name="side-by-side-migration"></a>並行遷移

在幾乎所有的遷移中，您都應該使用並行遷移路徑。 在並列式遷移中，您可以在執行 Office 通訊伺服器 2007 R2 的對應伺服器旁，使用 Lync Server 2013 部署新的伺服器，然後將作業轉移到新的伺服器。 如果需要回滾到 Office 通訊伺服器 2007 R2，您只需要將操作移回原始伺服器。 請注意，在這種情況下，使用升級後的用戶端排程的新會議將無法運作，而且用戶端也必須降級。

</div>

<div>

## <a name="coexistence-testing"></a>共存測試

在與 Office 通訊伺服器 2007 R2 並行部署 Lync Server 2013 之後，拓朴代表 Lync Server 2013 與 Office 通訊伺服器 2007 R2 的共存測試狀態。 當處於這個狀態時，請務必先測試並確定服務已啟動、可管理每個網站，而且用戶端可以與目前與舊版使用者通訊。 在遷移所有使用者之前，請務必瞭解每個部署的狀態，並確保每個部署都能正常運作且正常運作。 通常，共存測試階段會在整個 Lync Server 2013 的試驗測試中存在。 在一段時間內，舊版使用者會移至 Lync Server 2013，以確保應用程式相容性及功能及功能正常運作。 先導測試之後，使用者和應用程式會移至 Lync Server 2013 的產品版本，而舊版池與 Office 通訊伺服器 2007 R2 的應用程式就會停用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

