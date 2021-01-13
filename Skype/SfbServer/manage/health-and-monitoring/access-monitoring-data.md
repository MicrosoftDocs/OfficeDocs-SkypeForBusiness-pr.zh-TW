---
title: 在商務用 Skype Server 中存取監控資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要：瞭解商務用 Skype Server 中使用的監控資料。
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826543"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>在商務用 Skype Server 中存取監控資料
 
**摘要：** 深入瞭解商務用 Skype Server 中使用的監控資料。
  
監控資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得詳細資料記錄資料，並 QoEMetrics 經驗品質資料。 這兩個資料庫沒有什麼特別之處;這表示可使用您一般用於存取及分析 SQL Server 資料的任何工具，存取儲存在這些資料庫中的資料。
  
您應考慮存取及分析監控資料的一個工具，就是商務用 Skype Server 監控報告。 監視報告是由 Microsoft SQL Server Reporting Service 所發佈的一組標準報告。 這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。 商務用 Skype server 隨附的監控報告可從商務用 skype server 部署嚮導中安裝，並已設定好商務用 skype Server 並加以監視。
  
如前文所述，監控報告需要使用 SQL Server 報表服務。 SQL server 報表服務可以在您安裝 SQL Server 的同時安裝，也可以在安裝 SQL Server 本身之後安裝。
  
如需詳細資訊，請參閱 [在商務用 Skype Server 中安裝監控報告](../../deploy/deploy-monitoring/install-monitoring-reports.md)主題。
  

