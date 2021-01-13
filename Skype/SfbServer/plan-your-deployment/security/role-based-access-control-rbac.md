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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>商務用 Skype Server (RBAC) 角色的存取控制
 
商務用 Skype 伺服器包括 Role-Based 存取控制 (RBAC) 群組，可讓您委派管理工作，同時維持高安全性的安全性。 這些群組是在樹系準備期間建立的。 如需樹系準備的詳細資訊，請參閱 [適用于商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)。 如需「樹系準備」所建立之特定群組的詳細資訊，請參閱部署檔中的 [商務用 Skype Server 中的樹系準備所進行的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 。
  
使用 RBAC，可藉由指派使用者給預先定義的系統管理角色，授與系統管理權限，包括 11 個預先定義角色，涵蓋許多常用系統管理工作。 每個角色都與商務用 Skype Server 管理命令介面 Cmdlet 的特定清單相關聯，允許執行該角色中的使用者。 您可以使用 RBAC 遵循「最低權限」的原則，使用者只會授與其工作需要的系統管理能力。 
  
在 [規劃角色型存取控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)時，可以找到有關 RBAC 角色的詳細資料。
