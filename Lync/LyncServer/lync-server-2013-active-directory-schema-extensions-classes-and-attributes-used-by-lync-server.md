---
title: Lync Server 2013： Lync Server 所使用的 Active Directory 架構擴充功能、類別和屬性
description: Lync Server 2013： Lync Server 所使用的 Active Directory 架構擴充功能、類別和屬性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beac778d3315573f4d5cc6cb9c827a3a2fce9d0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567949"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="cbb23-103">Lync Server 2013 使用的 Active Directory 架構擴充功能、類別及屬性</span><span class="sxs-lookup"><span data-stu-id="cbb23-103">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbb23-104">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="cbb23-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="cbb23-105">本參考區段包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cbb23-105">This reference section includes the following information:</span></span>

  - <span data-ttu-id="cbb23-106">適用于 Lync Server 2013 的 Active Directory 架構擴充功能（新的或已變更的）</span><span class="sxs-lookup"><span data-stu-id="cbb23-106">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="cbb23-107">Active Directory 架構包含可以在 Active Directory 樹系中建立之每個物件類別的正式定義。</span><span class="sxs-lookup"><span data-stu-id="cbb23-107">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="cbb23-108">架構也包含可以存在於 Active Directory 物件上的每個屬性的正式定義。</span><span class="sxs-lookup"><span data-stu-id="cbb23-108">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="cbb23-109">Active Directory 通用類別目錄包含樹系所有物件的複本，以及每個物件的屬性子集。</span><span class="sxs-lookup"><span data-stu-id="cbb23-109">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="cbb23-110">本節說明 Lync Server 2013 中新增或變更的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="cbb23-110">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="cbb23-111">Lync Server 使用的所有類別，以及每個類別的描述</span><span class="sxs-lookup"><span data-stu-id="cbb23-111">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="cbb23-112">Lync Server 使用的所有屬性，以及每個屬性的描述</span><span class="sxs-lookup"><span data-stu-id="cbb23-112">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="cbb23-113">Lync Server 所使用的類別清單，具有每個類別的屬性可能包含</span><span class="sxs-lookup"><span data-stu-id="cbb23-113">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="cbb23-114">全域設定和物件，以及樹系準備期間建立的泛型服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="cbb23-114">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="cbb23-115">在網域準備期間，在網域根和內建容器上建立的 (Ace) 中的存取控制專案</span><span class="sxs-lookup"><span data-stu-id="cbb23-115">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="cbb23-116">在 Active Directory 組織單位 () 的授與 Test-cssetuppermission 指令程式中所做的變更 \_ 。</span><span class="sxs-lookup"><span data-stu-id="cbb23-116">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="cbb23-117">授與 Grant-csoupermission Cmdlet 對 Active Directory OU 所做的變更 \_ 。</span><span class="sxs-lookup"><span data-stu-id="cbb23-117">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cbb23-118">本章節內容</span><span class="sxs-lookup"><span data-stu-id="cbb23-118">In This Section</span></span>

  - [<span data-ttu-id="cbb23-119">Lync Server 2013 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="cbb23-119">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="cbb23-120">Lync Server 2013 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="cbb23-120">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="cbb23-121">Lync Server 2013 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="cbb23-121">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="cbb23-122">Lync Server 2013 中依類別的架構屬性</span><span class="sxs-lookup"><span data-stu-id="cbb23-122">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="cbb23-123">Lync Server 2013 中的樹系準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="cbb23-123">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="cbb23-124">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="cbb23-124">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="cbb23-125">Lync Server 2013 中 Grant-CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="cbb23-125">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="cbb23-126">Lync Server 2013 中 Grant-CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="cbb23-126">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

