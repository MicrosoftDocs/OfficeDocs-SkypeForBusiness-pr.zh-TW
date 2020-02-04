---
title: 群組呼叫裝貨配置先決條件與使用者權利
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的群組呼叫裝貨配置先決條件和使用者權利

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

[群組通話挑選] 是在您部署企業語音時預設安裝的通話管理功能。 本主題描述您必須具備的位置，才能設定群組呼叫拾取，以及執行設定工作所需的使用者權限。

本節假設您已閱讀與群組通話相關的規劃檔（請參閱[在 Lync Server 2013 中規劃群組通話挑選](lync-server-2013-planning-for-group-call-pickup.md)）。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>群組呼叫裝貨配置先決條件

群組呼叫挑選需要下列元件：

  - 應用程式服務

  - 通話駐留應用程式

當您部署企業語音時，系統會自動安裝這些元件。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>群組通話配置使用者權利

您可以使用下列管理工具來設定群組呼叫挑選：

  - Lync Server 管理命令介面

  - SEFAUtil 資源套件工具

使用 Lync Server 管理命令介面在 [通話駐留軌道] 表格中建立和管理呼叫挑選群組。 使用 SEFAUtil 資源套件工具指派呼叫挑選群組，並為使用者啟用群組呼叫分揀，或停用群組呼叫給使用者。

設定群組呼叫挑選需要下列任何系統管理角色，視任務而定：

  - **CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定與原則。

  - **CsUserAdministrator：** 此系統管理員角色可以為使用者啟用群組呼叫分揀。 此系統管理員角色也具有所有語音設定的唯讀視圖存取權。

  - **CsServerAdministrator：** 這個系統管理員角色可以管理、監視及疑難排解伺服器與服務。

  - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有工作。

<div>


> [!NOTE]
> 如需系統管理權利的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。



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

