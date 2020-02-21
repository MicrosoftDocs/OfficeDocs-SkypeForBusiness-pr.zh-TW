---
title: 從集區移除前端伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e9cd348d6a96009e92dfa8a3ef50dae39eb013d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>從集區移除前端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

Microsoft Lync Server 2010 Enterprise Edition 前端伺服器不能存在於做為獨立的電腦。 它必須定義為前端集區，即使有只有單一電腦集區中。

本主題會引導您完成程序移除現有前端集區中的個別前端伺服器。 如果前端伺服器集區中的最後一部伺服器，或如果您要完全移除集區，請參閱[移除前端集區或 Standard Edition server](remove-front-end-pool-or-standard-edition-server.md)。 沒有需要移除個別前端伺服器，然後再移除前端集區。 當您移除集區時，即會移除每個前端伺服器。

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>從集區移除前端伺服器

1.  開啟 Lync Server 2013 前端伺服器]，再開啟拓撲產生器]。

2.  瀏覽至 [Lync Server 2010] 節點。

3.  依序展開 [ **Enterprise Edition 前端集區]**，依序展開 [前端集區與前端伺服器，您想要移除，以滑鼠右鍵按一下您要移除以前端伺服器，然後按一下 [**刪除**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

