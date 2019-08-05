---
title: 商務用 Skype Server 的以角色為基礎的存取控制 (RBAC)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 商務用 Skype 伺服器包括角色式存取控制 (RBAC) 群組, 可讓您委派管理工作, 同時維持高安全性的標準。 這些群組是在林準備期間建立的。 如需林準備的詳細資料, 請參閱適用于商務用 Skype Server 的 Active Directory 網域服務。 如需有關林準備所建立之特定群組的詳細資訊, 請參閱部署檔中的商務用 Skype Server 中的 [由目錄林準備所做的變更]。
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2019
ms.locfileid: "36194096"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>商務用 Skype Server 的以角色為基礎的存取控制 (RBAC)
 
商務用 Skype 伺服器包括角色式存取控制 (RBAC) 群組, 可讓您委派管理工作, 同時維持高安全性的標準。 這些群組是在林準備期間建立的。 如需林準備的詳細資料, 請參閱[適用于商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)。 如需有關林準備所建立之特定群組的詳細資訊, 請參閱部署檔中的[商務用 Skype Server 中的 [由目錄林準備所做的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)]。
  
使用 RBAC, 系統會將使用者指派給預先定義的管理角色, 包括11個預先定義的角色, 涵蓋許多常見的管理工作, 以獲得 [RBAC] 許可權。 每個角色都與該角色中的使用者允許執行的商務用 Skype Server Management Shell Cmdlet 特定清單相關聯。 您可以使用 RBAC 來遵循「最低許可權」的原則, 在此原則中, 使用者只能得到他們工作所需的管理能力。 
  
在[針對角色式存取控制規劃](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)中, 可以找到有關 RBAC 角色的更多詳細資料。
