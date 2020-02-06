---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含使用者的用戶端喜好設定。 這通常是由 Lync 2013 舊版用戶端使用。
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814551"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含使用者的用戶端喜好設定。 這通常是由 Lync 2013 舊版用戶端使用。

**分欄**


| **左欄**            | **類型**                        | **說明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | Nvarchar （255），not null  <br/> | 具有以下格式的標籤： \<使用者 sip uri\>                   |
| prefSeqID  <br/>      | int，not null  <br/>            | 用於進行版本設定的順序編號（每個標籤）。  <br/> |
| prefContent  <br/>    | Nvarchar （max）  <br/>           | 已編碼的內容。  <br/>                                         |
| lastModifiedBy  <br/> | int，not null  <br/>            | 更新喜好設定的主體 ID。  <br/>         |

**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主鍵。  <br/> |


