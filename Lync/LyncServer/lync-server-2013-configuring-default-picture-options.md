---
title: Lync Server 2013：設定預設圖片選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f41fa8fb590b2f5bc2e38db9a72545e13fb8d73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>在 Lync Server 2013 中設定預設圖片選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-22_

根據預設，使用者的圖片會自動顯示。 如果使用者想要隱藏其圖片，可以在 Lync 用戶端中選取 [**隱藏我的圖片**] 選項。 不過，某些其他 Office 應用程式會忽略此設定。

如果您想要在使用者關閉時顯示圖片，您可以在全域或網站或服務中變更 Lync 圖片顯示設定，以便預設不會顯示使用者的圖片。 使用下列 Lync Server 管理命令介面 Cmdlet，在用戶端中明確選取 [**顯示我的圖片**] 選項，就不會顯示使用者的圖片：

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 。

</div>

<span> </span>

</div>

</div>

</div>

