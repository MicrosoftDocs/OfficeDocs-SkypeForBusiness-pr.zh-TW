---
title: Lync Server 2013：指定可用於登入 Lync Server 2013 的用戶端應用程式
description: Lync Server 2013：指定可用於登入 Lync Server 2013 的用戶端應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 907f4b99f1aa87ccee62ad39fdaccad1aa9d256d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558369"
---
# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="f9a1a-103">指定可用於登入 Lync Server 2013 的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="f9a1a-103">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9a1a-104">_**主題上次修改日期：** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="f9a1a-104">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="f9a1a-105">Lync Server 2013 可讓您指定環境中支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-105">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="f9a1a-106">使用用戶端版本原則可協助減少支援多個用戶端版本相關的成本。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-106">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="f9a1a-107">它也可以改善整體使用者經驗，因為當舊版用戶端與更新版本互動時，舊版的用戶端就可以限制可用的功能。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-107">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="f9a1a-108">用戶端版本控制有三個元件：</span><span class="sxs-lookup"><span data-stu-id="f9a1a-108">There are three components of client version control:</span></span>

  - <span data-ttu-id="f9a1a-109">用戶端版本設定可用來開啟或關閉用戶端版本控制，不論是全域性或針對特定網站。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-109">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="f9a1a-110">用戶端版本原則是用來全域指派一組規則，或指派給特定網站、集區或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-110">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="f9a1a-111">用戶端版本原則規則組成用戶端版本原則，用來定義當使用者嘗試以特定用戶端和用戶端版本登入時應採取的動作。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-111">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9a1a-112">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="f9a1a-112">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9a1a-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f9a1a-113">In This Section</span></span>

  - [<span data-ttu-id="f9a1a-114">Lync Server 2013 中的用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="f9a1a-114">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="f9a1a-115">Lync Server 2013 中的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="f9a1a-115">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="f9a1a-116">Lync Server 2013 中的用戶端版本規則</span><span class="sxs-lookup"><span data-stu-id="f9a1a-116">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9a1a-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9a1a-117">See Also</span></span>


[<span data-ttu-id="f9a1a-118">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="f9a1a-118">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

