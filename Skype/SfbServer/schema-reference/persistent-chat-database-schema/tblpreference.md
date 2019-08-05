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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含使用者的用戶端喜好設定。 這通常是由 Lync 2013 舊版用戶端使用。
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192729"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 包含使用者的用戶端喜好設定。 這通常是由 Lync 2013 舊版用戶端使用。

**分欄**


| **左欄**            | **類型**                        | **說明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | Nvarchar (255), not null  <br/> | 具有以下格式的標籤: \<使用者 sip uri\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | 用於進行版本設定的順序編號 (每個標籤)。  <br/> |
| prefContent  <br/>    | Nvarchar (max)  <br/>           | 已編碼的內容。  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | 更新喜好設定的主體 ID。  <br/>         |

**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主鍵。  <br/> |


