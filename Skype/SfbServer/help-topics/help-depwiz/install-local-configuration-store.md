---
title: 安裝本機組態存放區
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要開始安裝新的商務用 Skype Server 2015 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。 本機設定存放區將充當商務用 Skype Server 中央管理存放區 (CMS) 的唯讀複本。 您必須以電腦的本機系統管理員身分登入您執行 [安裝本機設定存放區] 步驟的伺服器，且擁有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 如果您在 Edge Server 上執行安裝程式，則您不必是 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員。 拓撲產生器定義檔會從匯出的定義檔讀取，而不是從中央管理存放區讀取。 若要匯出拓撲產生器定義檔，並將其提供給 Edge Server，請參閱匯出拓撲及將其複製到 Edge 安裝的外部媒體主題。
ms.openlocfilehash: e6634d90cba0c8ff07b6aa7a2c058e1dce467dc7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843136"
---
# <a name="install-local-configuration-store"></a>安裝本機組態存放區

若要開始安裝新的商務用 Skype Server 2015 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。 本機設定存放區將充當商務用 Skype Server 中央管理存放區 (CMS) 的唯讀複本。 您必須以電腦的本機系統管理員身分登入您執行 **[安裝本機設定存放區]** 步驟的伺服器，且擁有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 如果您在 Edge Server 上執行安裝程式，則您不必是 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員。 拓撲產生器定義檔會從匯出的定義檔讀取，而不是從中央管理存放區讀取。 若要匯出拓撲產生器定義檔，並將其提供給 Edge Server，請參閱 [匯出拓撲及將其複製到 Edge 安裝的外部媒體](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)主題。

若要開始安裝：

1. 在 [商務用 Skype Server 2015] 頁面上，按一下 [**步驟1：安裝本機設定存放區**] 旁邊的 [**執行**]。

2. 在 [ **本機伺服器** 設定] 頁面上，確定已選取 [ **自動從中央管理存放區取得** 設定] 選項，然後按 **[下一步]**。

3. 當本機伺服器設定安裝完成時，按一下 **[完成]**。

> [!NOTE]
> 安裝本機 SQL Server 可能需要一些時間。 安裝 SQL Server 時，將不會在安裝摘要畫面上看到進行中的更新。 如果您想要監視安裝進度，請使用 [工作管理員] 來觀賞 SQL Server 設定。