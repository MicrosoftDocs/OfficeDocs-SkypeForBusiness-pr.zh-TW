---
title: 商務用 Skype Server (RBAC) 角色的存取控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 商務用 Skype 伺服器包括 Role-Based 存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性的安全性。 這些群組是在樹系準備期間建立的。 如需樹系準備的詳細資訊，請參閱適用于商務用 Skype Server 的 Active Directory 網域服務。 如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔中的商務用 Skype Server 中的樹系準備所進行的變更。
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832103"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="a5f42-106">商務用 Skype Server (RBAC) 角色的存取控制</span><span class="sxs-lookup"><span data-stu-id="a5f42-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="a5f42-107">商務用 Skype 伺服器包括 Role-Based 存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性的安全性。</span><span class="sxs-lookup"><span data-stu-id="a5f42-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="a5f42-108">這些群組是在樹系準備期間建立的。</span><span class="sxs-lookup"><span data-stu-id="a5f42-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="a5f42-109">如需樹系準備的詳細資訊，請參閱 [適用于商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a5f42-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="a5f42-110">如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔中的 [商務用 Skype Server 中的樹系準備所進行的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="a5f42-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="a5f42-111">使用 RBAC，可藉由指派使用者給預先定義的系統管理角色，授與系統管理權限，包括 11 個預先定義角色，涵蓋許多常用系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="a5f42-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="a5f42-112">每個角色都與商務用 Skype Server 管理命令介面 Cmdlet 的特定清單相關聯，允許執行該角色中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a5f42-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="a5f42-113">您可以使用 RBAC 遵循「最低權限」的原則，使用者只會授與其工作需要的系統管理能力。</span><span class="sxs-lookup"><span data-stu-id="a5f42-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="a5f42-114">在 [規劃角色型存取控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)時，可以找到有關 RBAC 角色的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a5f42-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
