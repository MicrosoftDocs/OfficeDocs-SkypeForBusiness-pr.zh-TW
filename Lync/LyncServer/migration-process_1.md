---
title: 移轉程序
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 752bd5dd75eeaf87e4fccd553d5d13da16855499
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515040"
---
# <a name="migration-process"></a>移轉程序

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

Lync Server 2013 的建議和支援的遷移程式是並列遷移程式。 本主題說明您為何應該使用並列遷移，也包含共存的相關資訊。

<div>

## <a name="side-by-side-migration"></a>並列遷移

幾乎在每種移轉時，您都應該使用並存移轉路徑。 在並列式遷移中，您可以使用 Lync Server 2013 和執行 Office 通訊伺服器 2007 R2 的相對應伺服器來部署新的伺服器，然後將作業轉移至新的伺服器。 若要回復到 Office 通訊伺服器 2007 R2，您只需要將作業移回原始伺服器。 請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。

</div>

<div>

## <a name="coexistence-testing"></a>共存測試

將 Lync Server 2013 與 Office 通訊伺服器 2007 R2 同時部署後，拓撲代表 Lync Server 2013 和 Office 通訊伺服器 2007 R2 的共存測試狀態。 在此狀態下，必須先進行測試並確定服務已啟動、可管理每個網站，且用戶端可以與目前和舊版使用者通訊。 移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。 通常，共存測試階段會存在於所有的 Lync Server 2013 試驗測試中。 舊版使用者會移至 Lync Server 2013 一段時間，以確保應用程式相容性和功能正常運作。 在試驗測試之後，使用者和應用程式會移至 Lync Server 2013 的實際執行版本，且舊版集區和 Office 通訊伺服器 2007 R2 的應用程式會終止。

</div>

</div>

<span> </span>

</div>

</div>

</div>

