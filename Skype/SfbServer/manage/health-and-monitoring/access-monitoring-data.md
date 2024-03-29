---
title: 存取商務用 Skype Server 中的監控資料
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要：瞭解商務用 Skype Server 中所用的監控資料。
---

# <a name="access-monitoring-data-in-skype-for-business-server"></a>存取商務用 Skype Server 中的監控資料
 
**總結：** 深入瞭解商務用 Skype Server 所用的監控資料。
  
監控資料會儲存在一組 SQL Server 資料庫中： LcsCdr 供詳細通話記錄資料，以及 QoEMetrics 經驗品質資料。 這兩個資料庫沒有什麼特別之處;這表示，您可以使用通常用於存取及分析 SQL Server 資料的任何工具，存取儲存在這些資料庫中的資料。
  
您應考慮存取及分析監控資料的一個工具，是商務用 Skype Server 監視報告。 監視報告是一組 Microsoft SQL Server 報表服務所發佈的標準報告。 這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。 監視報告附帶商務用 Skype Server，而且可以在安裝商務用 Skype Server 之後從商務用 Skype Server 部署嚮導進行安裝，並已設定監視。
  
如前文所述，監控報告需要使用 SQL Server 報表服務。 SQL Server 報表服務可在您安裝 SQL Server 的同時安裝，也可以在安裝 SQL Server 後的任何時間安裝。
  
如需詳細資訊，請參閱[商務用 Skype Server 中的主題安裝監視報告](../../deploy/deploy-monitoring/install-monitoring-reports.md)。
  

