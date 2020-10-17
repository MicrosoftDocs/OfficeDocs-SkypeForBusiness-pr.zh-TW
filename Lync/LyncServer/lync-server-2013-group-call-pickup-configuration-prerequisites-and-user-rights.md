---
title: 群組呼叫收取設定必要條件和使用者權限
description: 群組呼叫收取設定必要條件和使用者權限。
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
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554449"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的群組呼叫收取設定必要條件和使用者權限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

「群組呼叫收取」是在您部署企業語音時，預設會安裝的通話管理功能。 本主題說明您必須準備好的功能，才能設定群組呼叫收取和執行設定工作所需的使用者權限。

本節假設您已閱讀與群組呼叫收取相關的規劃檔 (請參閱 [在 Lync Server 2013) 中規劃群組呼叫收取](lync-server-2013-planning-for-group-call-pickup.md) 。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>群組呼叫收取設定必要條件

群組呼叫收取需要下列元件：

  - 應用程式服務

  - Call Park application

當您部署企業語音時，會自動安裝這些元件。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>群組呼叫收取設定使用者權限

您可以使用下列系統管理工具來設定群組呼叫收取：

  - Lync Server 管理命令介面

  - SEFAUtil 資源套件工具

使用 Lync Server 管理命令介面來建立及管理通話駐留軌道表格中的呼叫收取群組。 使用 SEFAUtil resource 工具組工具指派呼叫收取群組，並為使用者啟用群組呼叫收取，或停用群組呼叫收取給使用者。

設定群組呼叫收取需要下列任何系統管理角色，視任務而定：

  - **CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定和原則。

  - **CsUserAdministrator：** 此系統管理員角色可以為使用者啟用群組呼叫收取功能。 其也具有所有語音設定的唯讀檢視存取權。

  - **CsServerAdministrator：** 此系統管理員角色可以管理、監控及疑難排解伺服器和服務。

  - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 及 CsUserAdministrator 的所有工作。

<div>


> [!NOTE]
> 如需系統管理許可權的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。



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

