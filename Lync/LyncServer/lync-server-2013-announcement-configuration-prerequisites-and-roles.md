---
title: Lync Server 2013：宣告組態先決條件和角色
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
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Lync Server 2013 中的宣告組態先決條件和角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

[宣告] 是企業語音通話管理功能。 本主題描述您必須具備的位置，才能設定宣告，以及您必須執行設定工作所需的角色指派。

本節假設您已閱讀與公告相關的規劃檔（請參閱[在 Lync Server 2013 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。

<div>

## <a name="announcement-configuration-prerequisites"></a>宣告設定先決條件

宣告應用程式需要下列元件：

  - 應用程式服務

  - 回應群組應用程式

  - 儲存音訊檔案的檔案存放區

當您部署企業語音時，系統會預設安裝這些元件。

</div>

<div>

## <a name="announcement-configuration-roles"></a>宣告配置角色

您可以使用下列管理工具來設定宣告：

  - Lync Server 控制台

  - Lync Server 管理命令介面

設定宣告應用程式需要下列其中一個管理角色：

  - **CsVoiceAdministrator**   此系統管理員角色可以建立、設定及管理所有語音相關設定與原則，包括宣告設定。

  - **CsServerAdministrator**   此系統管理員角色可以管理、監控及疑難排解伺服器與服務，以及設定所有宣告設定。

  - **CsAdministrator**   此系統管理員角色可以執行所有系統管理工作，並修改所有設定。

  - **CsViewOnlyAdministrator**   此系統管理員角色可以查看部署，以監控部署健康情況。

<div>


> [!NOTE]  
> 如需系統管理使用者權利的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署企業版語音](lync-server-2013-deploying-enterprise-voice.md)  


[規劃 Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

