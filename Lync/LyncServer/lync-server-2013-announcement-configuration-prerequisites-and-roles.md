---
title: Lync Server 2013： 宣告組態先決條件和角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dde28cac806b517a410f5edfa7ecbcf19176ed4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>宣告組態先決條件和 Lync Server 2013 中的角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-25_

宣告是企業語音通話管理功能。 本主題說明您需要備妥之前您可以設定宣告和角色指派，您需要先執行組態工作。

本節假設您已閱讀有關宣告的規劃文件 （請參閱[Planning for Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。

<div>

## <a name="announcement-configuration-prerequisites"></a>宣告設定先決條件

宣告應用程式需要下列元件：

  - 應用程式服務

  - 回應群組應用程式

  - 用來存放音訊檔案的檔案存放區

當您部署企業語音時，預設會安裝上述所有元件。

</div>

<div>

## <a name="announcement-configuration-roles"></a>宣告設定角色

您可以使用下列系統管理工具來設定宣告：

  - Lync Server 控制台

  - Lync Server 管理命令介面

設定應用程式需要下列其中一個下列管理角色的宣告：

  - **CsVoiceAdministrator**   此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則，包括宣告設定。

  - **CsServerAdministrator**   此系統管理員角色可以管理、 監控及疑難排解伺服器和服務，及設定所有宣告設定。

  - **CsAdministrator**   此系統管理員角色可以執行所有系統管理工作，並修改所有設定。

  - **CsViewOnlyAdministrator**   此系統管理員角色可以檢視部署，以監控部署健康情況。

<div>


> [!NOTE]  
> 如需管理使用者權限的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。



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

