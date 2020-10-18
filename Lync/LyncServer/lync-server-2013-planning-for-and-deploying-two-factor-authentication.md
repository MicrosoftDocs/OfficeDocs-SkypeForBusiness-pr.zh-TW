---
title: Lync Server 2013：規劃及部署雙因素驗證
description: Lync Server 2013：規劃及部署雙因素驗證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1e04fa7a0c1184152328882a7c7b4bea8e42ec0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579499"
---
# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="f7974-103">Lync Server 2013 中的雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="f7974-103">Two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7974-104">_**主題上次修改日期：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="f7974-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="f7974-105">雙因素驗證可要求使用者符合兩個驗證準則，以改善安全性：使用者名稱/密碼組合和 token 或憑證。</span><span class="sxs-lookup"><span data-stu-id="f7974-105">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="f7974-106">這也稱為「您所掌握的專案」，您知道的是什麼。」</span><span class="sxs-lookup"><span data-stu-id="f7974-106">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="f7974-107">具有憑證之雙因素驗證的典型範例是使用智慧卡。</span><span class="sxs-lookup"><span data-stu-id="f7974-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="f7974-108">智慧卡包含與使用者帳戶相關聯的憑證，而且可針對伺服器上儲存的使用者和憑證資訊驗證。</span><span class="sxs-lookup"><span data-stu-id="f7974-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="f7974-109">透過比較使用者資訊 (使用者名稱和密碼) 所提供的憑證，伺服器就會驗證認證，並驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="f7974-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7974-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f7974-110">In This Section</span></span>

[<span data-ttu-id="f7974-111">在 Lync Server 2013 中規劃雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="f7974-111">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="f7974-112">在 Lync Server 2013 中設定雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="f7974-112">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="f7974-113">使用 Lync 用戶端和 Lync Server 2013 的雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="f7974-113">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

