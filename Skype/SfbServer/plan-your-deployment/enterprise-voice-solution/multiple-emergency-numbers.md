---
title: 在商務用 Skype Server 中規劃多個緊急號碼
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 閱讀此主題以瞭解如何在商務用 Skype Server 中規劃多個緊急號碼。
ms.openlocfilehash: eb5fbc55bc7f2e783fbfa98c7bc7fb6db67ff748
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813863"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃多個緊急號碼
 
閱讀此主題以瞭解如何在商務用 Skype Server 中規劃多個緊急號碼。
  
商務用 Skype 伺服器現在支援為用戶端設定多個緊急號碼。 多個緊急數位是2016年6月累積更新所引進的新功能。 當美國有單一緊急號碼911時，許多國家/地區都支援多個緊急號碼。 例如，英國可支援999、英國專用的緊急號碼和112（歐盟的緊急號碼）。 
  
這項功能也適用于美國的保健服務提供者，其可提供多個程式碼的「藍色緊急」號碼的漫遊支援。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多個緊急號碼和位置原則

您可以建立位置原則，以定義要如何執行緊急通話的位置原則，以設定緊急通話。 您可以使用位置原則來定義產生緊急通話的號碼，例如，美國的911。999和112在英國。 位置原則決定使用者是否啟用緊急通話，以及行為是緊急通話的行為。 您也可以定義是否應自動通知公司的安全性，以及如何路由通話。
  
如需定義及修改位置原則的詳細資訊，請參閱[在商務用 Skype server 中](../../deploy/deploy-enterprise-voice/create-location-policies.md)[規劃商務用 skype 伺服器的位置原則](location-policies.md)及建立位置原則。 下列主題說明有關位置原則的概念;不過，您必須依照在 [商務用 Skype 中設定多個緊急號碼](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 的指示來設定多個緊急號碼。
  
在規劃多個緊急號碼時，請記住下列事項：
  
- 在2016年6月的累計更新中，您最多可以為指定的位置原則定義5個緊急數位。 在2016年11月累積更新中，這個數目會增加到100。
    
    > [!NOTE]
    > 若尚未升級至2016年11月累積更新，請參閱 [更新至商務用 Skype Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 針對每個緊急電話號碼，您可以指定零個或多個緊急撥號對應遮罩，這對於特定位置原則而言是唯一的。
    
    撥號遮罩是您想要在撥號時，轉譯為 [緊急撥號號碼] 值的數位。 例如，假設您在此欄位中輸入212的值，而 [緊急撥號號碼] 欄位的值為911。 當使用者撥打212時，此號碼會轉譯為911。 這可讓您撥打備用的緊急號碼，並且仍然可以撥打緊急服務 (例如，如果來自國家或地區具有不同緊急號碼的某人嘗試撥打該國家或地區的號碼，而不是其目前在) 中的國家或地區號碼。 您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。 例如，212; 414。 撥號遮罩的字串限制是100個字元。 每個字元必須是 0 到 9 的數字。
    
- 每個位置原則都有單一公用交換電話網路 (PSTN) 使用方式，用來判斷用來從使用這個原則的用戶端路由緊急通話的語音路由。 使用方式可以有每個緊急號碼的唯一路由。
    
- 如果位置原則同時定義了 EmergencyNumbers 和 DialString 參數，且用戶端支援多個緊急號碼，則緊急號碼優先。 如果用戶端不支援多個緊急號碼，則會使用緊急撥號字串。
    
- 如需有關商務用 Skype 和 Lync 用戶端支援接收多個緊急號碼、撥號遮罩和公用交換電話網路 (PSTN) 使用方式的詳細資訊，請參閱 [Client support](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 您無法使用商務用 Skype 控制台來設定多個緊急號碼。 您必須使用 PowerShell 來設定多個緊急號碼。 
  
設定多個緊急數位之前，請記住下列事項：
  
- 若要設定多個緊急號碼，您必須使用 New-CsEmergencyNumber Cmdlet，而且您必須透過使用 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 及 [Set CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet 指定 EmergencyNumbers 參數，來定義支援一個以上緊急號碼的位置原則。
    
- 如果您已使用 Set-CsLocationPolicy 或 New-CsLocationPolicy Cmdlet 使用 EmergencyDialString 和 EmergencyDialMask 參數定義現有的號碼，則使用 EmergencyNumbers 參數所指定的值將優先于舊值。 也就是說，EmergencyDialString 及 EmergencyDialMask 參數的值會被忽略。
    
- 如果您已使用 Set-CsLocationPolicy 或 New-CsLocationPolicy Cmdlet 使用 EmergencyDialString 和 EmergencyDialMask 參數定義現有的號碼，  *但未設定新的緊急號碼*  ，則會繼續使用現有號碼。
    
- 若要使用多個緊急號碼功能，您執行的用戶端版本必須能夠支援新功能。 舊版用戶端將繼續使用 Set-CsLocationPolicy 所指定的舊值，或使用 EmergencyDialString 和 EmergencyDialMask 參數 New-CsLocationPolicy Cmdlet。 
    
- 如果使用者要撥打符合撥號字串的號碼，則不需要撥號遮罩。 例如，如果使用者撥打的號碼是911，撥號字串是911，而且不需要任何遮罩。 
    
如需設定多個緊急號碼的詳細資訊，請參閱 [在商務用 Skype 中設定多個緊急號碼](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表顯示範例位置原則 (的範例，並非所有屬性都會顯示) ：
  

|**位置原則名稱**|**啟用 E911**|**緊急撥號字串**|**撥號遮罩**|**緊急電話號碼**|**PSTN 使用方式**|**需要位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美國  <br/> |是  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|倫敦  <br/> |是  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美國** -沒有多個緊急數位的需求。 在美國，您可以使用舊的緊急撥號字串和撥號遮罩設定。
  
 **華南-醫院** ：不需要遮罩 "450"。 若用戶端尚不支援多個緊急號碼，您可以使用舊的緊急撥號字串和撥號對應表設定。 針對支援多個緊急號碼的用戶端，您可以同時定義 "911" 和 "450" 的緊急號碼，而不是遮罩450。
  
 **倫敦** -針對尚未支援多個緊急號碼的用戶端，您可以使用舊的緊急撥號字串和撥號遮罩設定。 針對支援多個緊急號碼的用戶端，您可以為 "999" 和 "112" 同時定義每個的遮罩的緊急號碼。
  
 **印度** -所有已部署的用戶端都支援多個緊急數位。 在印度，您只需要設定多個緊急號碼。
  
## <a name="client-support"></a>用戶端支援
<a name="BKMK_Clients"> </a>

下表顯示多個緊急號碼的用戶端支援。 Microsoft 將繼續測試及發行其他用戶端的支援。 請經常查閱網站。

|**Windows**|**版本**|
|:-----|:-----|
|**隨選即用** <br/> |在5月10日 2016-版本1604上發行的 (目前通道)  (組建 6868.2062)   <br/> |
||FRDC (First Release Current 通道) 發行于2016年6月14日-版本 1605 (組建 6965.2058)   <br/> |
||DC (延期通道) ，2016年10月11日發行-版本 1605 (組建 6965.2092)   <br/> |
|**MSI** <br/> |更新-6 月7日更新- [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||商務用 Skype Mac 用戶端版本16。9  <br/> 商務用 Skype iOS 用戶端版本6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||商務用 Skype Android 用戶端版本6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip and Aastra 6725ip 電話機-2016 年9月累積更新 (組建 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 電話-9 月2016累計更新 (組建 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 電話機-2016 年9月累積更新 (組建 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

