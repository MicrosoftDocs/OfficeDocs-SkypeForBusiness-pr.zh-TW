---
title: Lync Server 2013： 指定可以用來登入 Lync Server 2013 的用戶端應用程式
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
ms.openlocfilehash: ea0083a28253f5b79e6124dc7733a3ea096f4509
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="74084-102">指定可以用來登入 Lync Server 2013 的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="74084-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74084-103">_**主題上次修改日期：** 2012年-12-11_</span><span class="sxs-lookup"><span data-stu-id="74084-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="74084-104">Lync Server 2013 可讓您指定的環境中支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="74084-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="74084-105">使用用戶端版本原則，可以協助減少支援多個用戶端版本的相關成本。</span><span class="sxs-lookup"><span data-stu-id="74084-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="74084-106">它也可以改善整體的使用者經驗，因為較早版本的用戶端時舊版和更新版本的用戶端互動，受限於可用的功能。</span><span class="sxs-lookup"><span data-stu-id="74084-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="74084-107">有三個元件的用戶端版本控制：</span><span class="sxs-lookup"><span data-stu-id="74084-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="74084-108">用戶端版本組態設定用來開啟用戶端版本控制，開啟或關閉，全域或針對特定網站。</span><span class="sxs-lookup"><span data-stu-id="74084-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="74084-109">用戶端版本原則用來指派一組規則全域，或特定站台，集區或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="74084-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="74084-110">用戶端版本原則規則構成用戶端版本原則]，並可用來定義使用者嘗試登入特定的用戶端與用戶端版本時應採取的動作。</span><span class="sxs-lookup"><span data-stu-id="74084-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74084-111">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="74084-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74084-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="74084-112">In This Section</span></span>

  - [<span data-ttu-id="74084-113">Lync Server 2013 中的用戶端版本組態設定</span><span class="sxs-lookup"><span data-stu-id="74084-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="74084-114">Lync Server 2013 中的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="74084-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="74084-115">Lync Server 2013 中的用戶端版本規則</span><span class="sxs-lookup"><span data-stu-id="74084-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74084-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74084-116">See Also</span></span>


[<span data-ttu-id="74084-117">管理裝置、 電話和 Lync Server 2013 中的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="74084-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

