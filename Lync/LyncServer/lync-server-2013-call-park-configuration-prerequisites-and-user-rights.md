---
title: Lync Server 2013：通話駐留設定必要條件和使用者權限
description: Lync Server 2013：通話駐留設定必要條件和使用者權限。
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
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563529"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留設定必要條件和使用者權限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

通話駐留是當您部署企業語音時，預設會安裝的通話管理功能。 本主題說明您必須準備好的功能，才能設定通話駐留和執行設定工作所需的使用者權限。

<div>


> [!IMPORTANT]  
> 通話駐留應用程式的自訂封存暫止檔案不會做為 Lync Server 2013 嚴重損壞修復程式的一部分，而且如果上傳至集區的檔案損毀、損毀或清除，檔案也會遺失。 請永遠為通話保留，保留您為通話保留所上傳之自訂音樂暫止檔案的個別備份副本。



</div>

本節假設您已閱讀與通話駐留相關的規劃檔 (請參閱 [在 Lync Server 2013) 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。

<div>

## <a name="call-park-configuration-prerequisites"></a>通話駐留設定必要條件

通話駐留需要下列元件：

  - 應用程式服務

  - Call Park application

當您部署企業語音時，會自動安裝這些元件。

如果希望來電者在通話駐留時可以聽到音樂，則需要等候音樂檔案。 當您部署企業語音時，會自動安裝預設的等候音樂檔案。 您可以用自己的等候音樂檔案取代預設檔案。 通話駐留使用檔案存放區以保留音訊檔。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>通話駐留設定使用者權限

您可以使用下列系統管理工具來設定通話駐留：

  - Lync Server 控制台

  - Lync Server 管理命令介面

您可以使用這些工具來設定通話駐留軌道表格，並設定通話駐留使用的其他設定。

設定通話駐留需要下列任何系統管理角色，視任務而定：

  - **CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定和原則。

  - **CsUserAdministrator：** 此系統管理員角色可以啟用語音原則中的通話駐留。 其也具有所有語音設定的唯讀檢視存取權。

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

