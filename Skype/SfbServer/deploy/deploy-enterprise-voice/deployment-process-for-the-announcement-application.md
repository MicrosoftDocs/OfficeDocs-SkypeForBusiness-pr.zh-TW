---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 在商務用 Skype Server Enterprise Voice 中宣告應用程式的部署程式和步驟。
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812303"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>商務用 Skype Server 中宣告應用程式的部署程式
 
在商務用 Skype Server Enterprise Voice 中宣告應用程式的部署程式和步驟。
  
宣告應用程式是一種企業語音功能，可讓您設定呼叫未指派的分機號碼 (對組織有效的分機，但未指派給人員或電話) 。 例如，您可以設定撥給未指派號碼的來電，以播放訊息或轉接至不同目的地，或兩者。
  
當您部署企業語音時，會將宣告應用程式安裝為前端伺服器或 Standard Edition Server 上的回應群組應用程式功能。 您需要設定宣告，作法為上傳音訊檔案或設定文字轉換語音 (TTS)，以及設定未指派的號碼表。
  
本節概述部署宣告應用程式所需的步驟。 您必須先部署 Enterprise Voice，才能設定宣告。 當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。
  
**宣告部署程序**

|**階段**|**步驟**|**角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|設定宣告設定  <br/> | 錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。 <br/>  設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[在商務用 Skype Server 中建立或刪除宣告](create-an-announcement.md) <br/> [在商務用 Skype Server 中建立或修改未指派號碼範圍](create-or-modify-an-unassigned-number-range.md) <br/> |
|驗證宣告部署  <br/> |透過接聽宣告以驗證設定如預期運作。  <br/> |-  <br/> |[ (選用) 在商務用 Skype 中驗證宣告部署](optional-verify-announcement-deployment.md) <br/> |
   

