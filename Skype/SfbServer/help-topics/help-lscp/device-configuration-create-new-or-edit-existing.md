---
title: 裝置設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 在「新增裝置設定」或「編輯裝置設定」頁面上，您可以建立或修改用以管理商務用 Skype 電話 Edition 的設定集合。 這些設定可讓您設定諸如所需的安全性模式、裝置記錄等級、語音服務品質 (QoS) 設定，以及電話是否應該在指定的非使用期限後自動鎖定等事項。
ms.openlocfilehash: 826f20dcd28002f293ebcf227a954f9bfd61c28f36fd4dd23414e2be59ef4f62
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302707"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>裝置組態：建立新的或編輯現有組態
 
在「**新增裝置** 設定」或「**編輯裝置** 設定」頁面上，您可以建立或修改用以管理商務用 Skype 電話 Edition 的設定集合。 這些設定可讓您設定諸如所需的安全性模式、裝置記錄等級、語音服務品質 (QoS) 設定，以及電話是否應該在指定的非使用期限後自動鎖定等事項。
  
## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「 **新增裝置** 設定」或「 **編輯裝置** 設定」頁面上執行下列工作：
  
- 新增裝置設定。
    
- 修改現有裝置設定的屬性。
    
## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。
  
- **範圍** 識別裝置設定的範圍 (Global 或 Site) 。
    
- **名稱** 您可以新增或修改裝置設定的名稱。
    
- **SIP 安全性** 您可以設定商務用 Skype 電話 Edition 裝置的傳輸和驗證需求。 您可以從下列選項中選取：
    
  - **低** 允許任何類型的授權或傳輸。
    
  - **中型** 使用者驗證需要 NTLM 或 Kerberos。
    
  - **高** SIP 連線需要 NTLM 或 Kerberos 才能進行使用者驗證，而 TLS 則是必要的。
    
- **記錄等級** 您可以在 UC 裝置上啟用記錄功能。 有效的值為： Off;低大中型和高。 預設值為 Off。
    
- **語音服務品質 (QoS)** 您可以指定從商務用 Skype 電話 Edition 裝置指派給語音流量 emanating 的 DSCP 值。 預設值為40。 不過，40不是一般用於音訊流量的值;相反地，音訊流量幾乎都是以 DSCP 碼46標示。 為了維持整個網路的一致性，您可能想要將此值變更為46。
    
- **電話鎖定** 您可以指定 UC 電話是否會在經過指定的閒置期限後自動鎖定自身。 您可以設定下列設定：
    
  - **強制執行裝置鎖定** 您可以選取此核取方塊強制執行裝置鎖定。
    
  - **最小 PIN 碼長度** 您可以指定用於解除電話鎖定之個人識別碼 (PIN) 的最小長度。 PIN 碼的長度範圍是四到15位數。 預設長度為六位數。
    
  - **電話鎖定** 超時您可以指定電話鎖定自身之前的最短時間長度。 -超時的範圍是0到60分鐘;預設值為10分鐘。 輸入值，格式為 HH： MM： SS。
    
## <a name="see-also"></a>另請參閱

[裝置組態](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)