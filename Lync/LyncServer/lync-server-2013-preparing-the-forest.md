---
title: Lync Server 2013：準備樹系
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35438969d8876875bef3d22b2d0ab676c146189
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506860"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a>準備 Lync Server 2013 的樹系

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

樹系準備會建立 Active Directory 全域設定和物件以及使用的 active directory 通用群組，以供 Lync Server 2013 使用，並授與 Active Directory 物件的適當存取權限。 如需通用群組和樹系準備所建立之全域設定和物件的描述，請參閱 [Lync Server 2013 中的樹系準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。

樹系準備也會建立包含 Lync Server 2013 所使用之屬性集及顯示說明符的物件，並將它們儲存在設定容器中。

<div>


> [!IMPORTANT]  
> 在執行樹系準備程式之前，請確定架構準備變更已複寫到所有網域控制站。 如果複寫未完成，則會發生錯誤。



</div>

如果您正在執行新的 Lync Server 部署，則必須將全域設定儲存在設定容器中。 如果您是從舊版升級，但仍將全域設定儲存在系統容器中，您可以繼續使用系統容器。

您必須是樹系根網域 Enterprise Admins 或 Domain Admins 群組的成員，才能執行這項程序。

<div>

## <a name="in-this-section"></a>本章節內容

  - [對 Lync Server 2013 執行樹系準備](lync-server-2013-running-forest-preparation.md)

  - [使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

