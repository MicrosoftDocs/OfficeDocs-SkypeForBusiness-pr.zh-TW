---
title: Lync Server 2013： Active Directory 基礎結構需求
description: Lync Server 2013： Active Directory 基礎結構需求。
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
ms.openlocfilehash: 62218605c9b3fac20743d0b6bb475515c9498f9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552359"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 基礎結構需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

在開始準備 Lync Server 2013 的 Active Directory 網域服務的程式之前，請確定您的 Active Directory 基礎結構符合下列必要條件：

  - 所有的網域控制站 (包含您部署 Lync Server 之樹系中的所有通用類別目錄伺服器) ，請執行下列其中一個作業系統：
    
      - Windows Server 2012 R2 作業系統
    
      - Windows Server 2012 作業系統
    
      - Windows Server 2008 R2 operating system
    
      - Windows Server 2008 作業系統
    
      - Windows Server 2008 Enterprise 32-位
    
      - 32位或64位版本的 Windows Server 2003 R2 作業系統
    
      - 32位或64位版本的 Windows Server 2003 作業系統

  - 所有部署 Lync Server 的網域都會引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的網域功能等級。

  - 您部署 Lync Server 的樹系會引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的樹系功能層級。
    
    <div>
    

    > [!NOTE]  
    > 若要變更您的網域或樹系功能等級，請參閱 TechNet 文件庫中的「提升網域和樹系功能等級」 <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> 。

    
    </div>

  - 在每個部署 Lync Server 電腦或使用者的網域中部署通用類別目錄。

Lync Server 2013 支援 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 及 Windows Server 2003 作業系統中的通用群組。 萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。 通用群組支援（結合系統管理員委派）可簡化 Lync Server 部署的管理。 例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。

</div>

<span> </span>

</div>

</div>

</div>

