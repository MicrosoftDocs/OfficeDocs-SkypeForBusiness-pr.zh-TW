---
title: Lync Server 2013： 通話駐留組態先決條件和使用者權限
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
ms.openlocfilehash: 2f357a840c4fdb08ea63e24b3a80394030dfbcb6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>通話駐留組態先決條件和 Lync Server 2013 中的使用者權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-10_

通話駐留是當您部署企業語音時，會將預設安裝的通話管理功能。 本主題說明您需要備妥之前您可以設定通話駐留以及您需要先執行組態工作的使用者權限。

<div>


> [!IMPORTANT]  
> 通話駐留應用程式的自訂等候音樂上保留檔案不會備份 Lync Server 2013 災害復原程序的一部分，如果損毀、 損毀，或清除上傳至集區的檔案，檔案將會遺失。 永遠保持個別檔案的備份自訂等候音樂上保留已上傳的通話駐留。



</div>

本節假設您已閱讀規劃通話駐留與相關的文件 （請參閱[Planning for Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。

<div>

## <a name="call-park-configuration-prerequisites"></a>通話駐留組態先決條件

通話駐留需要下列元件：

  - 應用程式服務

  - Call Park application

當您部署企業語音時，都會自動安裝這些元件。

如果希望來電者在通話駐留時可以聽到音樂，則需要等候音樂檔案。 當您部署企業語音時，會自動安裝預設的等候音樂上保留檔案。 您可以用自己的等候音樂檔案取代預設檔案。 通話駐留使用檔案存放區來保留音訊檔案。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>通話駐留設定使用者權限

您可以使用下列系統管理工具來設定通話駐留：

  - Lync Server 控制台

  - Lync Server 管理命令介面

若要設定通話駐留軌道表，並設定通話保留所使用的其他設定，您可以使用這些工具。

設定通話駐留要求任何下列系統管理角色，視工作而定：

  - **CsVoiceAdministrator:** 此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則。

  - **CsUserAdministrator:** 此系統管理員角色可以在語音原則中啟用通話駐留。 其也具有所有語音設定的唯讀檢視存取權。

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

