---
title: 規劃商務用 Skype Server 中的多個緊急電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 請閱讀本主題，瞭解如何在商務用 Skype Server 中規劃多個緊急電話號碼。
ms.openlocfilehash: 6f10b5c22a26a42f33f2a3b453dd2e244c9f32ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815961"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>規劃商務用 Skype Server 中的多個緊急電話號碼
 
請閱讀本主題，瞭解如何在商務用 Skype Server 中規劃多個緊急電話號碼。
  
商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。 多重緊急數位是2016年6月累計更新中所引進的新功能。 雖然美國只有一個緊急號碼（911），但許多國家/地區都支援多個緊急電話號碼。 例如，英國支援999、英國專用的緊急號碼和112（即歐盟的緊急電話號碼）。 
  
此功能也適用于美國的醫療保健供應商，且想要有多個程式碼的漫遊支援藍色緊急電話號碼。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多個緊急數量和位置原則

您可以透過建立位置原則來設定緊急通話，以定義將如何執行緊急通話。 您可以使用位置原則來定義哪些數位會產生緊急通話，例如，在美國是 911;999和112（英國）。 位置原則會判斷使用者是否已啟用緊急通話，以及是否有緊急通話的行為。 您也可以定義企業安全性是否應該自動收到通知，以及如何路由通話。
  
如需定義及修改位置原則的詳細資訊，請參閱[在商務用 Skype server 中](../../deploy/deploy-enterprise-voice/create-location-policies.md)[規劃商務用 Skype server](location-policies.md)和建立位置原則的位置原則。 下列主題說明有關位置原則的概念;不過，您必須依照在[商務用 Skype 中設定多個緊急數位](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的指示來設定多個緊急電話號碼。
  
規劃多個緊急數位時，請記住下列事項：
  
- 使用2016年6月累計更新，您最多可以為指定的位置原則定義5個緊急電話號碼。 在2016年11月累計更新中，此數位會增加到100。
    
    > [!NOTE]
    > 如果您尚未升級至2016年11月累計更新，請參閱[商務用 Skype Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 針對每個緊急電話號碼，您可以指定零個或多個緊急撥號遮罩，這些遮罩對於指定的位置原則而言是唯一的。
    
    撥號遮罩是您在撥入時，您想要轉換成 [緊急撥入號碼] 值的數位。 例如，假設您在這個欄位中輸入212的值，而 [緊急電話撥入號碼] 欄位的值為911。 當使用者撥打212時，該號碼會轉換為911。 這可讓您撥打備用的緊急電話號碼，而且仍能撥打電話給緊急服務（例如，如果某個國家或地區有不同緊急號碼的人嘗試撥打該國家或地區的號碼，而不是他們目前所在的國家或地區）。 您可以使用分號來分隔值，以定義多個緊急撥號遮罩。 例如，212; 414。 撥號遮罩的字串限制為100個字元。 每個字元都必須是數位0到9。
    
- 每個定位原則都有單一的公用交換電話網絡（PSTN）用法，用來判斷哪種語音路線是用來從使用這個原則的用戶端路由緊急電話。 使用方式可以有每個緊急數位的唯一路線。
    
- 如果位置原則已定義 EmergencyNumbers 和 DialString 參數，且用戶端支援多個緊急數位，則會優先處理緊急數位。 如果用戶端不支援多個緊急電話號碼，則會使用 [緊急撥號字串]。
    
- 如需商務用 Skype 和 Lync 用戶端支援接收多個緊急號碼、撥號遮罩及公用交換電話網絡（PSTN）用法的相關資訊，請參閱[用戶端支援](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 您無法使用商務用 Skype 的 [控制台] 來設定多個緊急號碼。 您必須使用 PowerShell 來設定多個緊急電話號碼。 
  
在您設定多個緊急電話號碼之前，請記住下列事項：
  
- 若要設定多個緊急電話號碼，您必須使用 CsEmergencyNumber Cmdlet，而且您必須定義支援多個緊急數位的位置原則，方法是將 EmergencyNumbers 參數指定為[新的-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet。
    
- 如果您使用 CsLocationPolicy 或 CsLocationPolicy Cmdlet （含 EmergencyDialString 和 EmergencyDialMask 參數）定義現有的數位，則使用 EmergencyNumbers 參數指定的值將會優先于舊相對值. 也就是說，EmergencyDialString 和 EmergencyDialMask 參數的值將會被忽略。
    
- 如果您已使用 CsLocationPolicy 或 CsLocationPolicy Cmdlet （含 EmergencyDialString 和 EmergencyDialMask 參數）定義現有的數位，*而您沒有設定新的緊急數位*，現有的數位仍會繼續使用。
    
- 若要使用多個緊急數量功能，您執行的用戶端版本必須能夠支援新功能。 較舊的用戶端會繼續使用 CsLocationPolicy 或 CsLocationPolicy Cmdlet 所指定的舊值，其中包含 EmergencyDialString 和 EmergencyDialMask 參數。 
    
- 如果使用者要撥打的號碼與撥號字串相符，則不需要撥號遮罩。 例如，如果使用者撥入的號碼是911，則撥號字串是911，且不需要遮罩。 
    
如需設定多個緊急電話號碼的詳細資訊，請參閱[在商務用 Skype 中設定多個緊急電話號碼](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表顯示範例位置原則（例如，在範例中不會顯示所有屬性）：
  

|**位置原則名稱**|**已啟用 E911**|**緊急撥號字串**|**撥號遮罩**|**緊急電話號碼**|**PSTN 使用量**|**需要位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美國  <br/> |是  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |是  <br/> |
|美國-醫院  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|位於  <br/> |是  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美國**—不需要多個緊急電話號碼。 在美國，您會使用舊的 [緊急撥號字串] 和 [撥號遮罩] 設定。
  
 **美國-醫院**：要求不要遮罩 "450"。 對於還不支援多個緊急號碼的客戶，您可以使用舊的 [緊急撥號字串] 和 [撥號遮罩] 設定。 針對支援多個緊急電話號碼的用戶端，您可以為 "911" 和 "450" （而非遮罩450）定義緊急號碼。
  
 **倫敦**：針對還不支援多個緊急電話號碼的用戶端，您可以使用舊的緊急撥號字串和撥號遮罩設定。 針對支援多個緊急電話號碼的用戶端，您可以為 "999" 和 "112" 定義一個緊急號碼，其中每個都有遮罩。
  
 **印度**-所有已部署的用戶端都支援多種緊急電話號碼。 在印度，您只需要設定多個緊急電話號碼。
  
## <a name="client-support"></a>用戶端支援
<a name="BKMK_Clients"> </a>

下表顯示多個緊急電話號碼的用戶端支援。 Microsoft 將繼續測試併發布對其他用戶端的支援。 請經常查看。

|**時間**|**版本**|
|:-----|:-----|
|**隨選即用** <br/> |在2016年5月10日發行的 CC （目前通道），版本1604（組建6868.2062）  <br/> |
||FRDC （第一次發行目前通道）于2016年6月14日-版本1605（組建6965.2058）發行  <br/> |
||在2016年10月11日發行的 DC （延遲通道）-版本1605（組建6965.2092）  <br/> |
|**.MSI** <br/> |年6月7日更新-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac 與 iOS** <br/> |**版本** <br/> |
||商務用 Skype Mac 用戶端版本16。9  <br/> 商務用 Skype iOS 用戶端版本6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||商務用 Skype Android 用戶端版本6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 電話-2016 年9月累計更新（組建7577.4512）-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 電話-9 月2016累積更新（組建7577.4512）-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 電話-2016 年9月累計更新（組建7577.4512）-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

