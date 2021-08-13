---
title: tblPreference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含使用者的用戶端喜好設定。 這通常是 Lync 2013 之前的用戶端使用。
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315429"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含使用者的用戶端喜好設定。 這通常是 Lync 2013 之前的用戶端使用。

**Columns**


| **欄**            | **類型**                        | **描述**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255)，非 null  <br/> | 標籤，格式如下： \<user sip uri\>                   |
| prefSeqID  <br/>      | int，非 null  <br/>            | 每個標籤的序數位 (，供版本設定之用) 。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | 編碼內容。  <br/>                                         |
| lastModifiedBy  <br/> | int，非 null  <br/>            | 更新首選項的主體識別碼。  <br/>         |

**機碼**

|**欄**|**描述**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主索引鍵。  <br/> |


