---
title: 控制台-簡介
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 本文提供新增控制台的概述。
ms.openlocfilehash: 8a4f8e073b424969951a69c620dd5f65a582fd75
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579793"
---
# <a name="control-panel"></a>控制台

目前的控制台是舊版控制台的新版本，其存在於一起。 新的控制台已存在於7月2019的累計更新中。 它可協助管理組織環境中的伺服器、使用者、用戶端和裝置的設定。

舊版控制台可能無法運作，因為 Silverlight 技術已于2021年10月12日到達「支援終止」階段。 如需詳細資訊，請參閱 [支援的 Silverlight 終止](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)。

> [!NOTE]
> 如需舊版控制台的資訊，請參閱 [控制台](../SfbServer/management-tools/install-and-open-administrative-tools.md)，然後流覽至 **商務用 Skype Server 控制台** 的區段。

## <a name="access-control-panel"></a>Access 控制台

若要在瀏覽器中啟動 [新增控制台]，請輸入 HTTPs:// &lt; 集區-FQDN &gt; /macp 或已設定的簡單 URL。

新的「控制台」包含的常用功能表項目目，可涵蓋組織的大部分需求。 舊版控制台中的某些功能表項目目無法在新控制台中使用。 不過，使用者可以使用 PowerShell Cmdlet 中的功能，以供使用者使用這些功能表項目中的功能。 如需詳細資訊，請參閱下表。

> [!NOTE]
> 其他功能表項目的檔將在後續使用中進行。

## <a name="client"></a>用戶端

|子功能表  |Cmdlet 的資訊來源  |
|---------|---------|
|用戶端版本原則         |    [用戶端版本原則](use-powershell-client-menu.md#client-version-policy)     |
|用戶端版本組態      |  [用戶端版本組態](use-powershell-client-menu.md#client-version-configuration)       |
|裝置更新    | [裝置更新](use-powershell-client-menu.md#device-update)        |
|測試裝置     | [測試裝置](use-powershell-client-menu.md#test-device)        |
|裝置記錄組態         |    [裝置記錄組態](use-powershell-client-menu.md#device-log-configuration)     |
|裝置設定         |    [裝置組態](use-powershell-client-menu.md#device-configuration)     |
|行動性原則         |    [行動性原則](use-powershell-client-menu.md#mobility-policy)     |
|推播通知設定         |    [推播通知設定](use-powershell-client-menu.md#push-notification-configuration)     |