---
title: Lync Server 2013：通話駐留組態先決條件和使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留組態先決條件和使用者權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

通話寄存是在您部署企業語音時預設安裝的通話管理功能。 本主題描述您必須具備的位置，才能設定通話駐留以及執行設定工作所需的使用者權限。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 災害復原程式中，不會備份通話駐留應用程式的自訂音樂保留式檔案，如果上傳至該池的檔案已損毀、損毀或被清除，這些檔案就會遺失。 針對通話駐留，請務必針對您上傳的自訂音樂保留檔案保留一個單獨的備份複本。



</div>

本節假設您已閱讀與電話寄存相關的規劃檔（請參閱[在 Lync Server 2013 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。

<div>

## <a name="call-park-configuration-prerequisites"></a>通話駐留設定先決條件

通話駐留需要下列元件：

  - 應用程式服務

  - 通話駐留應用程式

當您部署企業語音時，系統會自動安裝這些元件。

如果您希望呼叫者在通話暫停時聽到音樂，也必須使用 [音樂保留] 檔案。 當您部署企業語音時，系統會自動安裝預設的音樂保留盤案。 您可以將預設檔案替換為您自己的 [等候音樂] 檔案。 通話寄存使用檔案存放區來儲存音訊檔案。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>通話駐留設定使用者權利

您可以使用下列管理工具來設定通話駐留：

  - Lync Server 控制台

  - Lync Server 管理命令介面

您可以使用這些工具來設定 [通話駐留軌道] 表格，並設定 [通話駐留] 使用的其他設定。

配置通話駐留需要下列任何系統管理角色，視任務而定：

  - **CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定與原則。

  - **CsUserAdministrator：** 此系統管理員角色可以在語音原則中啟用通話駐留。 此系統管理員角色也具有所有語音設定的唯讀視圖存取權。

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

