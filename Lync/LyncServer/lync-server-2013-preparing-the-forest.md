---
title: Lync Server 2013： 準備樹系
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
ms.openlocfilehash: b9ab1ea2180c8fa4ba4f40cbf621816fe41ea7f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>準備樹系的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

樹系準備建立 Active Directory 全域設定和物件與 Lync Server 2013 中，所使用的 Active Directory 萬用群組，並授與 Active Directory 物件的適當存取權限。 萬用群組與全域設定和樹系準備所建立的物件的描述，請參閱[Lync Server 2013 中的樹系準備所進行的變更](lync-server-2013-changes-made-by-forest-preparation.md)。

樹系準備也會建立包含屬性設定，並顯示規範 Lync Server 2013 中，所使用的物件，並將其儲存在 [Configuration] 容器。

<div>


> [!IMPORTANT]  
> 請確定該結構描述準備變更複寫到所有網域控制站執行樹系準備程序之前。 如果複寫未完成，則會發生錯誤。



</div>

如果您執行新的 Lync Server 部署，您必須在 [Configuration] 容器中儲存全域設定。 如果您從較早版本升級，而且您仍然在系統容器中儲存全域設定，您可以繼續使用系統容器。

您必須是樹系根網域 Enterprise Admins 或 Domain Admins 群組的成員，才能執行這項程序。

<div>

## <a name="in-this-section"></a>本章節內容

  - [執行 Lync Server 2013 的樹系準備](lync-server-2013-running-forest-preparation.md)

  - [使用 cmdlet 反向樹系準備 Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

