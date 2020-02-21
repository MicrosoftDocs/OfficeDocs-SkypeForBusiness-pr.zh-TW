---
title: Lync 2013 的 Lync Server 2013： 群組原則設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937869dffc3dfecc994f3c9ce819e1a644c88abe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的群組原則設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

在舊版的 Lync 及 Office Communicator，獨立的 Communicator.adm 系統管理範本是適用於設定用戶端的群組原則設定。 Lync 2013 的新系統管理範本檔案 （.admx 和.adml 檔案） 會包含以及 Office 群組原則系統管理範本。 Lync 2013.admx 和.adml 檔案的可用性可讓您下載範本，並集中管理所有 Office 程式及語言套件的群組原則設定。 如需詳細資訊，請參閱 「 Office 2013 Administrative Template files （ADMX，ADML） 」 中的 Office 2013 文件<https://go.microsoft.com/fwlink/p/?linkid=267516>。

<div>

## <a name="client-bootstrapping-policies"></a>用戶端啟動原則

有幾個用戶端啟動原則是您必須在使用者第一次登入伺服器之前設定的。 因為在用戶端登入並開始從伺服器接收頻內佈建設定之前，這些原則就已生效，所以您可以使用 [群組原則] 來設定它們。 如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的設定用戶端啟動載入原則](lync-server-2013-configuring-client-bootstrapping-policies.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

