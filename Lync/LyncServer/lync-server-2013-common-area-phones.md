---
title: Lync Server 2013：常見的區域電話
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
ms.openlocfilehash: 71fa61773a4801d2050d67d4e86458eb5d37759c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="a8c98-102">Lync Server 2013 中的常見區域手機</span><span class="sxs-lookup"><span data-stu-id="a8c98-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8c98-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a8c98-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a8c98-104">常見的區域電話是不與個別使用者相關聯的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="a8c98-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="a8c98-105">一般的區域手機通常位於建立大廳、cafeterias、員工 lounges、會議室，以及許多人可能收集的其他位置，而不是在某人的辦公室中。</span><span class="sxs-lookup"><span data-stu-id="a8c98-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="a8c98-106">與 Lync Server 中的其他電話不同，通常是使用指派給個別使用者的語音原則和撥號方案進行維護，而一般的區域電話則不會有指派給他們的個別使用者。</span><span class="sxs-lookup"><span data-stu-id="a8c98-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="a8c98-107">這表示它們的管理方式必須與其他手機不同。</span><span class="sxs-lookup"><span data-stu-id="a8c98-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="a8c98-108">若要管理常見的局域網，您可以為所有您的通用區域電話（例如使用者帳戶）建立 Active Directory 網域服務連絡人物件，以獲指派策略和語音方案。</span><span class="sxs-lookup"><span data-stu-id="a8c98-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="a8c98-109">這種方法可讓您維持對常見區域手機的控制權，即使這些手機沒有與個別使用者相關聯也一樣。</span><span class="sxs-lookup"><span data-stu-id="a8c98-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="a8c98-110">您可以使用本節中的主題來瞭解如何為常用的區域手機建立連絡人物件、修改及刪除它們，以及設定及查看有關部署中常見區域手機的配置資訊。</span><span class="sxs-lookup"><span data-stu-id="a8c98-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8c98-111">您有三個適用于常見區域手機的選項： Aastra 6721ip 常見區域手機、HP 4110 IP 手機，以及 Polycom CX500 IP 通用區域電話。</span><span class="sxs-lookup"><span data-stu-id="a8c98-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="a8c98-112">Polycom CX3000 IP 會議電話是另一個變種常見的區域電話。</span><span class="sxs-lookup"><span data-stu-id="a8c98-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="a8c98-113">不過，它是用在會議室中。</span><span class="sxs-lookup"><span data-stu-id="a8c98-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="a8c98-114">如需常見區域電話的詳細資料，請參閱<A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">選擇新裝置</A>的 [通用區域電話] 區段。</span><span class="sxs-lookup"><span data-stu-id="a8c98-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8c98-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="a8c98-115">In This Section</span></span>

  - [<span data-ttu-id="a8c98-116">在 Lync Server 2013 中查看常見區域電話資訊</span><span class="sxs-lookup"><span data-stu-id="a8c98-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="a8c98-117">在 Lync Server 2013 中建立或修改常見的區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="a8c98-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="a8c98-118">在 Lync Server 2013 中啟用或停用熱 desking</span><span class="sxs-lookup"><span data-stu-id="a8c98-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="a8c98-119">在 Lync Server 2013 中刪除常見的區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="a8c98-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="a8c98-120">在 Lync Server 2013 中將原則指派至常見的區域電話</span><span class="sxs-lookup"><span data-stu-id="a8c98-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

