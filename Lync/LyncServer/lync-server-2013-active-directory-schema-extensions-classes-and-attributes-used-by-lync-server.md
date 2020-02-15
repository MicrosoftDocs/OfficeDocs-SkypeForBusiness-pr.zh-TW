---
title: 'Lync Server 2013: Active Directory 架構延伸模組、 類別及 Lync Server 所使用的屬性'
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
ms.openlocfilehash: 6868c98fd8ba78514d1e88c52075cbcccc50719b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="a49ac-102">Active Directory 架構延伸模組、 類別及 Lync Server 2013 所使用的屬性</span><span class="sxs-lookup"><span data-stu-id="a49ac-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a49ac-103">_**主題上次修改日期：** 2012年-06-19_</span><span class="sxs-lookup"><span data-stu-id="a49ac-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="a49ac-104">此參考一節包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a49ac-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="a49ac-105">Active Directory 架構延伸模組的全新或已變更的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49ac-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="a49ac-106">Active Directory 結構描述包含可以在 Active Directory 樹系中建立的每個物件類別的正式定義。</span><span class="sxs-lookup"><span data-stu-id="a49ac-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="a49ac-107">結構描述也包含可存在於 Active Directory 物件每個屬性的正式定義。</span><span class="sxs-lookup"><span data-stu-id="a49ac-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="a49ac-108">Active Directory 通用類別目錄包含所有物件的樹系，以及針對每個物件的屬性的部分的複本。</span><span class="sxs-lookup"><span data-stu-id="a49ac-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="a49ac-109">本小節會說明類別和 Lync Server 2013 中新增或變更的屬性。</span><span class="sxs-lookup"><span data-stu-id="a49ac-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="a49ac-110">每個描述 Lync Server 所使用的所有類別</span><span class="sxs-lookup"><span data-stu-id="a49ac-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="a49ac-111">每個描述 Lync Server 所使用的所有屬性</span><span class="sxs-lookup"><span data-stu-id="a49ac-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="a49ac-112">使用 Lync Server 與每個屬性的類別清單可能包含</span><span class="sxs-lookup"><span data-stu-id="a49ac-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="a49ac-113">通用設定和物件，以及在樹系準備時建立的萬用服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="a49ac-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="a49ac-114">存取控制項目 (Ace) 時，所建立的網域根目錄和內建容器上網域準備</span><span class="sxs-lookup"><span data-stu-id="a49ac-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="a49ac-115">在 Active Directory 組織單位 (OU) 中授與所進行的變更\_CsSetupPermission 指令程式。</span><span class="sxs-lookup"><span data-stu-id="a49ac-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="a49ac-116">在 Active Directory OU 中授與所進行的變更\_Grant-csoupermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a49ac-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a49ac-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a49ac-117">In This Section</span></span>

  - [<span data-ttu-id="a49ac-118">Lync Server 2013 中的結構描述變更</span><span class="sxs-lookup"><span data-stu-id="a49ac-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="a49ac-119">架構類別和 Lync Server 2013 中的描述</span><span class="sxs-lookup"><span data-stu-id="a49ac-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="a49ac-120">架構屬性和 Lync Server 2013 中的描述</span><span class="sxs-lookup"><span data-stu-id="a49ac-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="a49ac-121">由 Lync Server 2013 中的類別的結構描述屬性</span><span class="sxs-lookup"><span data-stu-id="a49ac-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="a49ac-122">Lync Server 2013 中的樹系準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="a49ac-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="a49ac-123">Lync Server 2013 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="a49ac-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="a49ac-124">Grant-cssetuppermission Lync Server 2013 中所做的變更</span><span class="sxs-lookup"><span data-stu-id="a49ac-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="a49ac-125">Grant-csoupermission Lync Server 2013 中所做的變更</span><span class="sxs-lookup"><span data-stu-id="a49ac-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

