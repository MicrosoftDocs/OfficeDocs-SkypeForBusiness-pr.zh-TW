---
title: 'Lync Server 2013: Active Directory 基礎結構需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的 active Directory 基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

在開始準備 Active Directory Domain Services for Lync Server 2013 的程序之前，請確定您的 Active Directory 基礎結構符合下列先決條件：

  - 所有網域控制站 （包括所有通用類別目錄伺服器） 部署 Lync Server 的樹系中都執行下列其中一個下列作業系統：
    
      - Windows Server 2012 R2 作業系統
    
      - Windows Server 2012 作業系統
    
      - Windows Server 2008 R2 operating system
    
      - Windows Server 2008 作業系統
    
      - Windows Server 2008 Enterprise 32 位元
    
      - 32 位元或 64 位元版本的 Windows Server 2003 R2 作業系統
    
      - 32 位元或 64 位元版本的 Windows Server 2003 作業系統

  - 您將部署 Lync Server 的所有網域會都引發為 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在網域功能等級最低的 Windows Server 2003。

  - 您將部署 Lync Server 的樹系會引發為 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在樹系功能等級最低的 Windows Server 2003。
    
    <div>
    

    > [!NOTE]  
    > 若要變更您的網域或樹系功能層級，請參閱 「 提高網域和樹系功能等級 > TechNet Library 中的<A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>。

    
    </div>

  - 您可在此部署 Lync Server 電腦或使用者每個網域中部署通用類別目錄。

Lync Server 2013 中的 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008 和 Windows Server 2003 作業系統支援萬用群組。 萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。 萬用群組支援，加上系統管理員委派，可簡化管理 Lync Server 部署。 例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。

</div>

<span> </span>

</div>

</div>

</div>

