---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 在商務用 Skype Server 企業語音中宣告應用程式的部署程式與步驟。
ms.openlocfilehash: e579ca3877b35ae5cdbb85582516a3bfbac8c354
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745359"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>商務用 Skype Server 中宣告應用程式的部署程式
 
在商務用 Skype Server 企業語音中宣告應用程式的部署程式與步驟。
  
宣告應用程式是企業語音的功能，可讓您設定對呼叫未指派的分機號碼所進行的呼叫， (擴充功能對您的組織有效，但未指派給人員或電話) 。 例如，您可以設定撥給未指派號碼的來電，以播放訊息或轉接至不同目的地，或兩者。
  
當您部署企業語音時，會將宣告應用程式安裝為前端伺服器或 Standard Edition Server 上的回應群組應用程式功能。 您需要設定宣告，作法為上傳音訊檔案或設定文字轉換語音 (TTS)，以及設定未指派的號碼表。
  
本節概述部署宣告應用程式所需的步驟。 您必須先部署企業語音，才能設定宣告。 當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。
  
**宣告部署程序**

|**階段**|**步驟**|**角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|設定宣告設定  <br/> | 錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。 <br/>  設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[在商務用 Skype Server 中建立或刪除宣告](create-an-announcement.md) <br/> [在商務用 Skype Server 中建立或修改未指派的號碼範圍](create-or-modify-an-unassigned-number-range.md) <br/> |
|驗證宣告部署  <br/> |透過接聽宣告以驗證設定如預期運作。  <br/> |-  <br/> |[ (選用) 在商務用 Skype 中驗證宣告部署](optional-verify-announcement-deployment.md) <br/> |
   

