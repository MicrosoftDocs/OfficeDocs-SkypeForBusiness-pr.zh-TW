---
title: Lync Server 2013：設定預設圖片選項
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
ms.openlocfilehash: fc6bb0368b97e41402f2e0abf0834cf23f078c08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514810"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="94529-102">在 Lync Server 2013 中設定預設圖片選項</span><span class="sxs-lookup"><span data-stu-id="94529-102">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94529-103">_**主題上次修改日期：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="94529-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="94529-104">依預設，會自動顯示使用者的圖片。</span><span class="sxs-lookup"><span data-stu-id="94529-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="94529-105">如果使用者想要隱藏其圖片，可在 Lync 用戶端中選取 [ **隱藏我的圖片** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="94529-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="94529-106">不過，有些其他 Office 應用程式會忽略此設定。</span><span class="sxs-lookup"><span data-stu-id="94529-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="94529-107">如果在使用者關閉時顯示圖片的可能性很重要，您可以變更全域或網站或服務的 Lync 圖片顯示設定，因此預設不會顯示使用者的圖片。</span><span class="sxs-lookup"><span data-stu-id="94529-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="94529-108">使用下列 Lync Server 管理命令介面 Cmdlet，除非使用者在用戶端明確選取 [ **顯示我的圖片** ] 選項，否則不會顯示使用者的圖片：</span><span class="sxs-lookup"><span data-stu-id="94529-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="94529-109">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) 。</span><span class="sxs-lookup"><span data-stu-id="94529-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

