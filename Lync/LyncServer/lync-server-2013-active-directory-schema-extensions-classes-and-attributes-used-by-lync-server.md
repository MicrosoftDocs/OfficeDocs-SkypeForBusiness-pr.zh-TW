---
title: Lync Server 2013：Lync Server 使用的 Active Directory 結構描述擴充功能、類別及屬性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc883c1c85acbe41bec6a25467e50800c036996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="7f2fa-102">Lync Server 2013 使用的 Active Directory 結構描述擴充功能、類別及屬性</span><span class="sxs-lookup"><span data-stu-id="7f2fa-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f2fa-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="7f2fa-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="7f2fa-104">本參考章節包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="7f2fa-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="7f2fa-105">Lync Server 2013 的新功能或已變更的 Active Directory 架構擴充功能</span><span class="sxs-lookup"><span data-stu-id="7f2fa-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="7f2fa-106">Active Directory 架構包含可在 Active Directory 林中建立的每個物件類別的正式定義。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="7f2fa-107">架構也包含可在 Active Directory 物件上存在的每個屬性的正式定義。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="7f2fa-108">Active Directory 通用類別目錄包含樹林所有物件的複本，以及每個物件的屬性子集。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="7f2fa-109">本節將說明 Lync Server 2013 中新增或變更的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="7f2fa-110">Lync Server 所使用的所有類別，以及每個類別的描述</span><span class="sxs-lookup"><span data-stu-id="7f2fa-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="7f2fa-111">Lync Server 所使用的所有屬性，以及每個屬性的描述</span><span class="sxs-lookup"><span data-stu-id="7f2fa-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="7f2fa-112">Lync Server 所使用之類別的清單，其中每個類別都可能包含</span><span class="sxs-lookup"><span data-stu-id="7f2fa-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="7f2fa-113">全域設定和物件，以及在林準備期間建立的泛型服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="7f2fa-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="7f2fa-114">在網域準備期間，在網域根目錄和內建容器中建立的存取控制專案（Ace）</span><span class="sxs-lookup"><span data-stu-id="7f2fa-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="7f2fa-115">由 Grant\_CsSetupPermission Cmdlet 在 Active Directory 組織單位（OU）上所做的變更。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="7f2fa-116">由 Grant\_CsOUPermission Cmdlet 在 ACTIVE Directory OU 上所做的變更。</span><span class="sxs-lookup"><span data-stu-id="7f2fa-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f2fa-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="7f2fa-117">In This Section</span></span>

  - [<span data-ttu-id="7f2fa-118">Lync Server 2013 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="7f2fa-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="7f2fa-119">Lync Server 2013 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="7f2fa-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="7f2fa-120">Lync Server 2013 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="7f2fa-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="7f2fa-121">Lync Server 2013 中依類別分類的架構屬性</span><span class="sxs-lookup"><span data-stu-id="7f2fa-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="7f2fa-122">Lync Server 2013 中的林準備所做的變更</span><span class="sxs-lookup"><span data-stu-id="7f2fa-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="7f2fa-123">在 Lync Server 2013 中由網域準備所做的變更</span><span class="sxs-lookup"><span data-stu-id="7f2fa-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="7f2fa-124">在 Lync Server 2013 中由 Grant CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="7f2fa-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="7f2fa-125">在 Lync Server 2013 中由 Grant CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="7f2fa-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

