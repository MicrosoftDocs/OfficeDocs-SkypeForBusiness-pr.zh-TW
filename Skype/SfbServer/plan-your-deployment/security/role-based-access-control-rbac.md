---
title: 商務用 Skype Server 的以角色為基礎的存取控制（RBAC）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 商務用 Skype 伺服器包括角色式存取控制（RBAC）群組，可讓您委派管理工作，同時維持高安全性的標準。 這些群組是在林準備期間建立的。 如需林準備的詳細資料，請參閱適用于商務用 Skype Server 的 Active Directory 網域服務。 如需有關林準備所建立之特定群組的詳細資訊，請參閱部署檔中的商務用 Skype Server 中的 [由目錄林準備所做的變更]。
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815621"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>商務用 Skype Server 的以角色為基礎的存取控制（RBAC）
 
商務用 Skype 伺服器包括角色式存取控制（RBAC）群組，可讓您委派管理工作，同時維持高安全性的標準。 這些群組是在林準備期間建立的。 如需林準備的詳細資料，請參閱[適用于商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)。 如需有關林準備所建立之特定群組的詳細資訊，請參閱部署檔中的[商務用 Skype Server 中的 [由目錄林準備所做的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)]。
  
使用 RBAC，系統會將使用者指派給預先定義的管理角色，包括11個預先定義的角色，涵蓋許多常見的管理工作，以獲得 [RBAC] 許可權。 每個角色都與該角色中的使用者允許執行的商務用 Skype Server Management Shell Cmdlet 特定清單相關聯。 您可以使用 RBAC 來遵循「最低許可權」的原則，在此原則中，使用者只能得到他們工作所需的管理能力。 
  
在[針對角色式存取控制規劃](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)中，可以找到有關 RBAC 角色的更多詳細資料。
