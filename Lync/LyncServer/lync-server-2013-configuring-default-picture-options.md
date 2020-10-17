---
title: Lync Server 2013：設定預設圖片選項
description: Lync Server 2013：設定預設圖片選項。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6261aca82b4c71eb8e0573e8d2adbfc008e743fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557999"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a>在 Lync Server 2013 中設定預設圖片選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-22_

依預設，會自動顯示使用者的圖片。 如果使用者想要隱藏其圖片，可在 Lync 用戶端中選取 [ **隱藏我的圖片** ] 選項。 不過，有些其他 Office 應用程式會忽略此設定。

如果在使用者關閉時顯示圖片的可能性很重要，您可以變更全域或網站或服務的 Lync 圖片顯示設定，因此預設不會顯示使用者的圖片。 使用下列 Lync Server 管理命令介面 Cmdlet，除非使用者在用戶端明確選取 [ **顯示我的圖片** ] 選項，否則不會顯示使用者的圖片：

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 。

</div>

<span> </span>

</div>

</div>

</div>

