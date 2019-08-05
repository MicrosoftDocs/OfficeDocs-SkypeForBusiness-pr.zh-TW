---
title: 商務用 Skype Server 中的會議詳細資料包表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '摘要: 瞭解商務用 Skype Server 中使用的會議詳細資料包表。'
ms.openlocfilehash: 5b88ae62c7d06437b3502bd72dd965fc26fbfcb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193750"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>商務用 Skype Server 中的會議詳細資料包表

**摘要:** 瞭解商務用 Skype Server 中所用的會議詳細資料包告。

[會議詳細資料] 報告提供參與會議之所有使用者的詳細資訊。 例如, 您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間, 以及用來將該使用者連線到會議的端點使用者代理程式。 您也可以在每個會議中查看使用者角色的資訊 (例如, 簡報者或出席者)。 最重要的是, 您會快速看到哪些使用者成功加入並完成會議, 哪些使用者無法順利加入並完成會議。

## <a name="accessing-the-conference-detail-report"></a>存取會議詳細資料包表

您可以從下列報表存取會議詳細資料包告:

- [[通話許可控制] 報告](call-admission-control-report.md)(按一下會議的詳細指標)

- [[失敗清單] 報告](failure-list-report.md)(按一下會議規格)

- [使用者活動報告](call-diagnostic-reports-per-user.md)(按一下會議 URI 躍點數)

在會議詳細資料包告中, 您可以按一下診斷報告 (詳細資料) 度量來存取[診斷 Repor](diagnostic-report.md) 。

## <a name="filters"></a>濾鏡

無。 您無法在會議詳細資料包表中篩選。

## <a name="metrics"></a>指標

下表列出在會議詳細資料包表的 [會議資訊] 區段中提供的資訊。

**會議資訊度量單位**


| **名稱**                 | **說明**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **會議 URI** <br/> | 指派給會議的 URI。 例如：  <br/> sip: kmyer@litwareinc.com; gruu; 不透明 = 應用程式: 會議: 焦點: id: drg2y8v4  <br/> |
| **池 FQDN** <br/>      | 會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱。  <br/>                             |
| **開始時間** <br/>     | 會議開始的日期和時間。  <br/>                                                                          |
| **召集人** <br/>      | 組織會議的使用者的 SIP 位址。  <br/>                                                               |
| **結束時間** <br/>       | 會議結束的日期和時間。  <br/>                                                                            |

下表列出會議詳細資料包表之會議參與區段中提供的資訊。

**會議參與指標**

|**名稱**|**說明**|
|:-----|:-----|
|**使用者名** <br/> |參與會議之使用者的 SIP 位址。  <br/> |
|**角色** <br/> |會議參與者所扮演的角色 (例如, 簡報者)。  <br/> |
|**連通** <br/> |參與者的網路連線 (通常是內部或外部的網路連線)。  <br/> |
|**加入時間** <br/> |參與者加入會議的日期和時間。  <br/> |
|**休假時間** <br/> |參與者離開會議的日期和時間。  <br/> |
|**使用者代理程式** <br/> |參與者終點所使用之軟體的識別碼。  <br/> |
|**診斷報告** <br/> |提供診斷及疑難排解資訊。 包括 SIP 回應代碼、診斷標頭、會議加入時間, 以及失敗會話的診斷 Id。  <br/> |

下表列出在會議詳細資料包表的 [會議形式] 區段中提供的資訊。

**會議形式度量單位**

|**名稱**|**說明**|
|:-----|:-----|
|**使用者名** <br/> |參與會議之使用者的 SIP 位址。  <br/> |
|**加入時間** <br/> |參與者加入會議的日期和時間。  <br/> |
|**休假時間** <br/> |參與者離開會議的日期和時間。  <br/> |
|**會議服務器 URI** <br/> |在會議中使用的會議服務器 URI。  <br/> |
|**診斷報告** <br/> |提供診斷及疑難排解資訊。 包括 SIP 回應代碼、診斷標頭、會議加入時間, 以及失敗會話的診斷 Id。  <br/> |


