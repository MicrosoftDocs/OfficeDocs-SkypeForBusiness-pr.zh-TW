---
title: Lync Server 2013：準備樹系
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>為 Lync Server 2013 準備樹系

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

林準備：建立 Active Directory 全域設定和物件與 Active Directory 通用群組供 Lync Server 2013 使用，並在 Active Directory 物件上授予適當的存取權限。 如需通用群組以及由林準備所建立之全域設定及物件的描述，請參閱[Lync Server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。

林準備也會建立包含 Lync Server 2013 所使用之屬性集和顯示說明符的物件，並將它們儲存在配置容器中。

<div>


> [!IMPORTANT]  
> 在執行目錄林準備程式前，請確定架構準備變更已複製到所有網網域控制站。 如果無法完成複製，就會發生錯誤。



</div>

如果您執行的是新的 Lync Server 部署，您必須將全域設定儲存在配置容器中。 如果您是從較舊的版本升級，但仍將全域設定儲存在系統容器中，您可以繼續使用系統容器。

您必須是林根網域之 [企業管理員] 或 [網域管理員] 群組的成員，才能執行此程式。

<div>

## <a name="in-this-section"></a>本節內容

  - [針對 Lync Server 2013 執行樹系準備](lync-server-2013-running-forest-preparation.md)

  - [使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

