---
title: 群組呼叫收取組態先決條件和使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d0127ff5c196c14dc7844c6958ced9ae5478113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>群組呼叫收取組態先決條件和 Lync Server 2013 中的使用者權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-30_

群組來電接聽是當您部署企業語音時，會將預設安裝的通話管理功能。 本主題說明您需要備妥之前您可以設定群組來電接聽與您需要先執行組態工作的使用者權限。

本節假設您已閱讀群組來電接聽與相關的規劃文件 （請參閱[Planning for Lync Server 2013 中的 [群組來電接聽](lync-server-2013-planning-for-group-call-pickup.md)）。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>群組通話收取組態先決條件

群組來電接聽需要下列元件：

  - 應用程式服務

  - Call Park application

當您部署企業語音時，都會自動安裝這些元件。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>群組通話收取設定使用者權限

您可以使用下列系統管理工具來設定群組來電接聽：

  - Lync Server 管理命令介面

  - SEFAUtil resource kit 工具

使用 Lync Server 管理命令介面來建立及管理通話駐留軌道表中的呼叫收取群組。 使用 SEFAUtil resource kit 工具，來指派通話收取群組，並為使用者啟用群組來電接聽或停用使用者的群組來電接聽。

設定群組來電接聽需要下列管理角色，根據任務的任何項目：

  - **CsVoiceAdministrator:** 此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則。

  - **CsUserAdministrator:** 此系統管理員角色可以針對使用者啟用群組來電接聽。 其也具有所有語音設定的唯讀檢視存取權。

  - **CsServerAdministrator:** 此系統管理員角色可以管理、 監控及疑難排解伺服器和服務。

  - **CsAdministrator:** 此系統管理員角色可以執行所有 CsVoiceAdministrator、 CsServerAdministrator 和 CsUserAdministrator 的工作。

<div>


> [!NOTE]
> 如需系統管理權限的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署 Lync Server 2013 中的 Enterprise Voice](lync-server-2013-deploying-enterprise-voice.md)  


[規劃 Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

