---
title: Lync Server 2013：Active Directory 基礎結構需求
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
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

開始準備 Lync Server 2013 的 Active Directory 網域服務的程式之前，請確認您的 Active Directory 基礎結構符合下列先決條件：

  - 在您部署 Lync Server 的林中，所有網網域控制站（包含所有通用類別目錄伺服器）都可執行下列其中一個作業系統：
    
      - Windows Server 2012 R2 作業系統
    
      - Windows Server 2012 作業系統
    
      - Windows Server 2008 R2 作業系統
    
      - Windows Server 2008 作業系統
    
      - Windows Server 2008 企業版32位
    
      - 32位或64位版本的 Windows Server 2003 R2 作業系統
    
      - 32位或64位版本的 Windows Server 2003 作業系統

  - 您在其中部署 Lync Server 的所有網域都會出現在 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows server 2008 或至少 Windows Server 2003 的網域功能層級。

  - 您在其中部署 Lync Server 的林會引發到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能層級。
    
    <div>
    

    > [!NOTE]  
    > 若要變更您的網域或林功能層級，請參閱 TechNet Library 中的「提升網域和林<A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>功能層級」。

    
    </div>

  - 全域編目是在您部署 Lync Server 電腦或使用者的每個網域中部署。

Lync Server 2013 支援 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 作業系統中的通用群組。 通用群組的成員可以包含網域樹狀結構或林中任何網域的其他群組和帳戶，而且可以在網域樹狀結構或樹林中的任何網域中指派許可權。 通用群組支援，與系統管理員委派結合，簡化 Lync Server 部署的管理。 例如，您不需要將一個網域新增至另一個網域，就能讓系統管理員同時管理兩者。

</div>

<span> </span>

</div>

</div>

</div>

