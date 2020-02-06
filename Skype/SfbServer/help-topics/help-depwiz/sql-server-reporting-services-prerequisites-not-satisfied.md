---
title: SQL Server Reporting Services (未滿足先決條件)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。
ms.openlocfilehash: 2c5f58751d03d5c482bd3b9113b764ffe626cec6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823447"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (未滿足先決條件)

如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。

若要解決此問題，請確定您已將監視伺服器加入網域，且已在拓撲結構建立程式中定義，且已發佈拓撲。 Sql server Reporting Services 也必須在 SQL Server 上提供，且在 SQL Server 上的 [監視伺服器] 資料庫中已安裝為功能。

如需詳細資訊，請參閱[在商務用 Skype Server 2015 中安裝監視報告](../../deploy/deploy-monitoring/install-monitoring-reports.md)和[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。


