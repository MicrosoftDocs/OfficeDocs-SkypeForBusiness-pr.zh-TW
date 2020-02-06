---
title: 在商務用 Skype Server 中存取監視資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要：瞭解商務用 Skype 伺服器中使用的監視資料。
ms.openlocfilehash: b4eca36a09c4aa56b7216b476e0f0c5fa06d7a45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818184"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>在商務用 Skype Server 中存取監視資料
 
**摘要：** 瞭解商務用 Skype 伺服器中使用的監視資料。
  
監視資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得呼叫詳細資料記錄資料，並 QoEMetrics 經驗資料的品質。 這兩個資料庫沒有任何特別之處;這表示儲存在那些資料庫中的資料可以使用任何您用來存取及分析 SQL Server 資料的工具存取。
  
您應該考慮存取及分析監視資料的一個工具，就是商務用 Skype Server 監視報告。 [監視報告] 是由 Microsoft SQL Server Reporting Services 發佈的一組標準報告。 這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。 在已安裝商務用 skype server 並已設定監視之後，就能從商務用 skype server 的 [商務用 skype server 部署] 嚮導中安裝監控報告。
  
如所述，監視報告需要使用 SQL Server Reporting Services。 您可以在安裝 SQL Server 的同時安裝 SQL Server Reporting Service，或在安裝 SQL Server 本身之後安裝。
  
如需詳細資訊，請參閱[在商務用 Skype Server 中安裝監視報告](../../deploy/deploy-monitoring/install-monitoring-reports.md)主題。
  

