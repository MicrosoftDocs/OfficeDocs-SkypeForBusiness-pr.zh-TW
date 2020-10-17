---
title: Lync Server 2013：宣告設定必要條件和角色
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
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531690"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Lync Server 2013 中的宣告設定必要條件和角色

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

宣告是企業語音通話管理功能。 本主題說明您必須準備好的功能，才能設定宣告以及執行設定工作所需的角色指派。

本節假設您已閱讀與宣告 (相關的規劃檔，請參閱 [在 Lync Server 2013) 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。

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

設定宣告應用程式需要下列其中一個系統管理角色：

  - **CsVoiceAdministrator**    此系統管理員角色可以建立、設定及管理所有與語音相關的設定和原則（包括宣告設定）。

  - **CsServerAdministrator**    此系統管理員角色可以管理、監控及疑難排解伺服器和服務，以及設定所有宣告設定。

  - **CsAdministrator**    此系統管理員角色可以執行所有系統管理工作並修改所有設定。

  - **CsViewOnlyAdministrator**    此系統管理員角色可以查看部署，以監視部署的健康情況。

<div>


> [!NOTE]  
> 如需系統管理使用者權限的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署企業語音](lync-server-2013-deploying-enterprise-voice.md)  


[在 Lync Server 2013 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

