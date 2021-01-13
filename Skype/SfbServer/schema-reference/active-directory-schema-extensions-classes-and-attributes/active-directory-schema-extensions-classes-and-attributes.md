---
title: Active Directory 結構描述擴充功能、類別及屬性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 本參考區段包含下列資訊：
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831933"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="6b9ed-103">Active Directory 結構描述擴充功能、類別及屬性</span><span class="sxs-lookup"><span data-stu-id="6b9ed-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="6b9ed-104">本參考區段包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6b9ed-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="6b9ed-105">適用于商務用 Skype Server 的 Active Directory 架構擴充功能（新的或已變更的）</span><span class="sxs-lookup"><span data-stu-id="6b9ed-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="6b9ed-106">Active Directory 架構包含可以在 Active Directory 樹系中建立之每個物件類別的正式定義。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="6b9ed-107">架構也包含可以存在於 Active Directory 物件上的每個屬性的正式定義。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="6b9ed-108">Active Directory 通用類別目錄包含樹系所有物件的複本，以及每個物件的屬性子集。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="6b9ed-109">本節說明商務用 Skype Server 中新的或已變更的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="6b9ed-110">商務用 Skype Server 所使用的所有類別，以及每個類別的描述</span><span class="sxs-lookup"><span data-stu-id="6b9ed-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6b9ed-111">商務用 Skype Server 所使用的所有屬性，以及每個屬性的描述</span><span class="sxs-lookup"><span data-stu-id="6b9ed-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6b9ed-112">商務用 Skype Server 所使用的類別清單，且每個類別的屬性都可能包含</span><span class="sxs-lookup"><span data-stu-id="6b9ed-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="6b9ed-113">全域設定和物件，以及樹系準備期間建立的泛型服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="6b9ed-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="6b9ed-114">在網域準備期間，在網域根和內建容器上建立的 (Ace) 中的存取控制專案</span><span class="sxs-lookup"><span data-stu-id="6b9ed-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="6b9ed-115">在 Active Directory 組織單位上進行的變更 (OU) Grant_CsSetupPermission Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="6b9ed-116">Grant_CsOUPermission Cmdlet 在 Active Directory OU 中所做的變更。</span><span class="sxs-lookup"><span data-stu-id="6b9ed-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6b9ed-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6b9ed-117">In This Section</span></span>

- [<span data-ttu-id="6b9ed-118">商務用 Skype Server 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="6b9ed-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="6b9ed-119">商務用 Skype Server 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="6b9ed-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="6b9ed-120">商務用 Skype Server 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="6b9ed-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="6b9ed-121">商務用 Skype Server 中的依類別分類的架構屬性</span><span class="sxs-lookup"><span data-stu-id="6b9ed-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="6b9ed-122">在商務用 Skype Server 中進行樹系準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="6b9ed-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="6b9ed-123">商務用 Skype Server 中的網域準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="6b9ed-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="6b9ed-124">在商務用 Skype Server 中 Grant-CsSetupPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="6b9ed-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="6b9ed-125">在商務用 Skype Server 中 Grant-CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="6b9ed-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

