---
title: 安裝本機設定存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝新的商務用 Skype Server 角色服務器，您必須先安裝將主持本機配置存放區的本機 SQL 伺服器。 本機配置存儲將充當商務用 Skype Server 中央管理商店（CMS）的唯讀複本。
ms.openlocfilehash: 51343bc68415d5c3a9b99b0697285f2e5c30d557
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705450"
---
# <a name="install-local-configuration-store"></a>安裝本機設定存放區

若要開始安裝新的商務用 Skype Server 角色服務器，您必須先安裝將主持本機配置存放區的本機 SQL 伺服器。 本機配置存儲將充當商務用 Skype Server 中央管理商店（CMS）的唯讀複本。 您必須以電腦的本機系統管理員身分登入伺服器 (您在伺服器上執行「安裝本機設定存放區」步驟)****，並具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 若要在 Edge Server 上執行安裝程式，便無需具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 會從匯出的定義檔（而不是從中央管理儲存體）讀取拓撲建立器定義檔。 若要匯出拓撲建立器定義檔，並將它提供給邊緣伺服器，請參閱[匯出拓撲並將它複製到外部媒體以進行 Edge 安裝](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)的主題。

若要開始安裝：

1. 在商務用 Skype Server 頁面上，按一下 [ **Step1：安裝本機配置存放區**] 旁的 [**執行**]。

2. 在「本機伺服器設定」**** 頁面上，確定已選取 [自動從中央管理存放區擷取設定]**** 選項，然後按 [下一步]****。

3. 當本機伺服器設定安裝完成時，按一下 [完成]****。

> [!NOTE]
> 安裝本機 SQL Server 可能需要一些時間。 在安裝 SQL Server 時，您將不會在安裝摘要畫面上看到所進行的更新。 如果您想要監視安裝進度，請使用 [工作管理員] 來觀察 SQL Server 設定。


