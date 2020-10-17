---
title: Lync Server 2013：公共區域電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5039fe3e47668a17196a81316250d7c517e6e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526140"
---
# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="f92ad-102">Lync Server 2013 中的公共區域電話</span><span class="sxs-lookup"><span data-stu-id="f92ad-102">Common area phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f92ad-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f92ad-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f92ad-104">常見的區域電話是與個別使用者沒有關聯的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="f92ad-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="f92ad-105">一般地區電話通常位於建立大廳、cafeterias、員工 lounges、會議室及其他大量人員可能收集的地方，而不是位於某人的辦公室。</span><span class="sxs-lookup"><span data-stu-id="f92ad-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="f92ad-106">與 Lync Server 中的其他電話不同的是，通常是使用指派給個別使用者的語音原則和撥號對應表來維護，但一般區域電話不會有個別的使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="f92ad-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="f92ad-107">這表示它們的管理方式必須不同于其他電話。</span><span class="sxs-lookup"><span data-stu-id="f92ad-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="f92ad-108">若要管理常見的區號，您可以為所有您可以指派原則及語音方案的一般區域電話建立 Active Directory 網域服務連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="f92ad-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="f92ad-109">這種方法可讓您維護一般區域電話的控制權，即使這些電話不會與個別使用者相關聯也是一樣。</span><span class="sxs-lookup"><span data-stu-id="f92ad-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="f92ad-110">使用本節中的主題，瞭解如何建立常見區域電話的連絡人物件、修改和刪除它們，以及設定及查看有關部署中常見區域電話的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="f92ad-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f92ad-111">一般區域電話有三個選項： Aastra 6721ip common area phone、HP 4110 IP Phone 及 Polycom CX500 IP 公共區域電話。</span><span class="sxs-lookup"><span data-stu-id="f92ad-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="f92ad-112">Polycom CX3000 IP 會議電話是另一個變種常見區域電話。</span><span class="sxs-lookup"><span data-stu-id="f92ad-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="f92ad-113">不過，此功能適用于會議室。</span><span class="sxs-lookup"><span data-stu-id="f92ad-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="f92ad-114">如需有關一般區域電話的詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">選擇新裝置</A>的通用區域電話一節。</span><span class="sxs-lookup"><span data-stu-id="f92ad-114">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f92ad-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f92ad-115">In This Section</span></span>

  - [<span data-ttu-id="f92ad-116">在 Lync Server 2013 中查看共同區域電話資訊</span><span class="sxs-lookup"><span data-stu-id="f92ad-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="f92ad-117">在 Lync Server 2013 中建立或修改公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="f92ad-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="f92ad-118">啟用或停用 Lync Server 2013 中的熱 desking</span><span class="sxs-lookup"><span data-stu-id="f92ad-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="f92ad-119">在 Lync Server 2013 中刪除公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="f92ad-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="f92ad-120">將 Lync Server 2013 中的原則指派給一般區域電話</span><span class="sxs-lookup"><span data-stu-id="f92ad-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

