---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187339"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>商務用 Skype Server 中宣告應用程式的部署程式
 
在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。
  
[宣告] 應用程式是一種企業語音功能, 可讓您設定呼叫未指派的延伸 (對貴組織有效, 但未指派給人員或電話的延伸)。 例如, 您可以設定未指派號碼的呼叫來播放郵件, 或將其傳送至不同的目的地, 或兩者皆可。
  
發佈應用程式是在您部署企業語音時, 在前端伺服器或標準版伺服器上作為回應群組應用程式的功能安裝。 您必須先上傳音訊檔案或設定文字轉換語音 (TTS) 及設定 [未指定的數位] 資料表來設定宣告。
  
本節概要說明部署宣告應用程式所需的步驟。 您必須先部署企業語音, 然後才能設定宣告。 當您部署企業語音時, 會安裝並啟用宣告應用程式所需的元件。
  
**發佈部署程式**

|**分**|**步驟**|**角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|設定宣告設定  <br/> | 透過錄製及上傳音訊檔案或使用文字轉換語音 (TTS) 來建立公告。 <br/>  在 [未指定的數位] 資料表中設定未指定的數位範圍, 並將它們與適當的宣告建立關聯。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[在商務用 Skype Server 中建立或刪除公告](create-an-announcement.md) <br/> [在商務用 Skype Server 中建立或修改未指定的數位範圍](create-or-modify-an-unassigned-number-range.md) <br/> |
|確認您的宣告部署  <br/> |透過聆聽宣告來測試, 以確認您的設定如預期的那樣正常運作。  <br/> |-  <br/> |[可選在商務用 Skype 中驗證宣告部署](optional-verify-announcement-deployment.md) <br/> |
   

