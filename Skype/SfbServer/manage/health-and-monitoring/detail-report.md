---
title: 商務用 Skype Server 中的會議詳細資料包告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 摘要：瞭解商務用 Skype Server 中所用的會議詳細資料包告。
ms.openlocfilehash: 56fafff71f1700667a2ad982f56db099cb60c45e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737799"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>商務用 Skype Server 中的會議詳細資料包告

**摘要：** 深入瞭解商務用 Skype Server 中所用的會議詳細資料包告。

「會議詳細資料報告」可提供參與會議之使用者的詳細資訊。例如，您可以查看使用者加入會議的日期和時間、使用者離開會議的日期和時間，以及用來將使用者與會議連線的端點使用者代理程式之類的資訊。您也可以查看使用者在每個會議中的角色 (例如，簡報者或是出席者)。更重要的是，您可以更快速地查看哪些使用者已順利加入並完成會議，而哪些使用者無法順利加入並完成會議。

## <a name="accessing-the-conference-detail-report"></a>存取會議詳細資料報告

您可從下列報告來存取會議詳細資料報告：

- [Call Admission Control Report](call-admission-control-report.md) (按一下會議的 [詳細資料] 計量)

- [Failure List Report](failure-list-report.md) (按一下 [會議] 計量)

- [User Activity Report](call-diagnostic-reports-per-user.md) (按一下 [會議 URI] 計量)

您還可從會議詳細資料報告中，按一下 [診斷報告] ([詳細資料]) 計量，來存取[Diagnostic Report](diagnostic-report.md)。

## <a name="filters"></a>篩選

無。您無法篩選會議詳細資料報告。

## <a name="metrics"></a>度量

下表列出會議詳細資料報告的「會議資訊」區段中所提供的資訊。

**會議資訊計量**


| **名稱**                 | **描述**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **會議 URI** <br/> | 指派給會議的 URI。例如：  <br/> sip： kmyer@litwareinc .com; gruu; 不透明 = 應用程式：會議： focus：識別碼： drg2y8v4  <br/> |
| **集區 FQDN** <br/>      | 工作階段所涉及的登錄器集區或 Edge Server 的完整網域名稱。  <br/>                             |
| **開始時間** <br/>     | 會議開始的日期與時間。  <br/>                                                                          |
| **召集人** <br/>      | 召開會議之使用者的 SIP 位址。  <br/>                                                               |
| **結束時間** <br/>       | 會議結束的日期與時間。  <br/>                                                                            |

下表列出會議詳細資料報告的「會議參與區段」中所提供的資訊。

**會議參與計量**

|**名稱**|**描述**|
|:-----|:-----|
|**使用者** <br/> |參與會議之使用者的 SIP 位址。  <br/> |
|**Role** <br/> |會議參與者所扮演的角色 (例如，簡報者)。  <br/> |
|**連線能力** <br/> |參與者的網路連線 (一般來說是從內部或從外部)。  <br/> |
|**加入時間** <br/> |參與者加入會議的日期與時間。  <br/> |
|**離開時間** <br/> |參與者離開會議的日期與時間。  <br/> |
|**使用者代理程式** <br/> |參與者的端點所使用的軟體識別碼。  <br/> |
|**診斷報告** <br/> |可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。  <br/> |

下表列出會議詳細資料包告之 [會議形式] 區段中所提供的資訊。

**會議形式計量**

|**名稱**|**描述**|
|:-----|:-----|
|**使用者** <br/> |參與會議之使用者的 SIP 位址。  <br/> |
|**加入時間** <br/> |參與者加入會議的日期與時間。  <br/> |
|**離開時間** <br/> |參與者離開會議的日期與時間。  <br/> |
|**會議伺服器 URI** <br/> |會議中所使用之會議伺服器的 URI。  <br/> |
|**診斷報告** <br/> |可提供診斷和疑難排解資訊，包括 SIP 回應碼、診斷標頭、會議加入時間以及失敗之工作階段的診斷識別碼。  <br/> |


