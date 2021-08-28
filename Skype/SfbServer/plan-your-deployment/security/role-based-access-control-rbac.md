---
title: '商務用 Skype Server 的角色型存取控制 (RBAC) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 商務用 Skype Server 包含 Role-Based 的存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性標準。 這些群組是在樹系準備期間建立的。 如需樹系準備的詳細資訊，請參閱 Active Directory 網域服務的商務用 Skype Server。 如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔中商務用 Skype Server 的「樹系準備」所做的變更。
ms.openlocfilehash: 1768c61f902dddb456f6a80bccf3b72bd9757f77
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627935"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>商務用 Skype Server 的角色型存取控制 (RBAC) 
 
商務用 Skype Server 包含 Role-Based 的存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性標準。 這些群組是在樹系準備期間建立的。 如需樹系準備的詳細資訊，請參閱[Active Directory 網域服務的商務用 Skype Server](active-directory-domain-services.md)。 如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔[中商務用 Skype Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)的「樹系準備」所做的變更。
  
使用 RBAC，可藉由指派使用者給預先定義的系統管理角色，授與系統管理權限，包括 11 個預先定義角色，涵蓋許多常用系統管理工作。 每個角色都與特定清單的商務用 Skype Server 管理命令介面 Cmdlet 相關聯，允許該角色中的使用者執行。 您可以使用 RBAC 遵循「最低權限」的原則，使用者只會授與其工作需要的系統管理能力。 
  
在 [規劃角色型存取控制](/lyncserver/lync-server-2013-planning-for-role-based-access-control)時，可以找到有關 RBAC 角色的詳細資料。