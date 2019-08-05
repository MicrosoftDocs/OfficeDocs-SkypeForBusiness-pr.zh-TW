---
title: Active Directory 架構擴充、類別和屬性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: '本參考章節包含下列資訊:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192926"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="be1f0-103">Active Directory 架構擴充、類別和屬性</span><span class="sxs-lookup"><span data-stu-id="be1f0-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="be1f0-104">本參考章節包含下列資訊:</span><span class="sxs-lookup"><span data-stu-id="be1f0-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="be1f0-105">商務用 Skype Server 的新功能或已變更的 Active Directory 架構擴充功能</span><span class="sxs-lookup"><span data-stu-id="be1f0-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="be1f0-106">Active Directory 架構包含可在 Active Directory 林中建立的每個物件類別的正式定義。</span><span class="sxs-lookup"><span data-stu-id="be1f0-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="be1f0-107">架構也包含可在 Active Directory 物件上存在的每個屬性的正式定義。</span><span class="sxs-lookup"><span data-stu-id="be1f0-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="be1f0-108">Active Directory 通用類別目錄包含樹林所有物件的複本, 以及每個物件的屬性子集。</span><span class="sxs-lookup"><span data-stu-id="be1f0-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="be1f0-109">本節將說明商務用 Skype Server 中新增或變更的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="be1f0-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="be1f0-110">商務用 Skype Server 所使用的所有班級, 以及每個課程的描述</span><span class="sxs-lookup"><span data-stu-id="be1f0-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="be1f0-111">商務用 Skype Server 所使用的所有屬性, 以及每個屬性的描述</span><span class="sxs-lookup"><span data-stu-id="be1f0-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="be1f0-112">商務用 Skype Server 所使用的類別清單, 其中的屬性可能包含</span><span class="sxs-lookup"><span data-stu-id="be1f0-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="be1f0-113">全域設定和物件, 以及在林準備期間建立的泛型服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="be1f0-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="be1f0-114">在網域準備期間, 在網域根目錄和內建容器中建立的存取控制專案 (Ace)</span><span class="sxs-lookup"><span data-stu-id="be1f0-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="be1f0-115">使用 Grant_CsSetupPermission Cmdlet 在 Active Directory 組織單位 (OU) 上所做的變更。</span><span class="sxs-lookup"><span data-stu-id="be1f0-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="be1f0-116">Grant_CsOUPermission Cmdlet 在 Active Directory OU 上所做的變更。</span><span class="sxs-lookup"><span data-stu-id="be1f0-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="be1f0-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="be1f0-117">In This Section</span></span>

- [<span data-ttu-id="be1f0-118">商務用 Skype Server 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="be1f0-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="be1f0-119">商務用 Skype Server 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="be1f0-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="be1f0-120">商務用 Skype Server 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="be1f0-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="be1f0-121">商務用 Skype Server 中按類別分類的架構屬性</span><span class="sxs-lookup"><span data-stu-id="be1f0-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- <span data-ttu-id="be1f0-122">[在商務用 Skype Server 的 [目錄林準備] 中所做的變更](changes-made-by-forest-preparation.md)</span><span class="sxs-lookup"><span data-stu-id="be1f0-122">[Changes made by forest preparation in Skype for Business Server](changes-made-by-forest-preparation.md)</span></span>
    
- [<span data-ttu-id="be1f0-123">在商務用 Skype Server 中由網域準備所做的變更</span><span class="sxs-lookup"><span data-stu-id="be1f0-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="be1f0-124">在商務用 Skype Server 中由 Grant CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="be1f0-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="be1f0-125">在商務用 Skype Server 中由 Grant CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="be1f0-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

