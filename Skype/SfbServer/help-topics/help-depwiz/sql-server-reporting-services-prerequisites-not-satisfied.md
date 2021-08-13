---
title: SQL Server Reporting Services (不符合必要條件)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 6c87bc180923442bfd1f32b6836a6d41256261d3fe3233b0f347071f6bf9e884
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304075"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (不符合必要條件)

如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。

若要解決此問題，請確定您已將監控伺服器加入至網域，該伺服器已在拓撲產生器中定義，而且拓撲已經發佈。 您也必須能夠在 SQL Server 上使用 SQL Server Reporting Services，並將其安裝成 SQL Server 上之監控伺服器資料庫中的功能。

如需詳細資訊，請參閱[Install monitoring Reports in 商務用 Skype Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md)和[部署監控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。