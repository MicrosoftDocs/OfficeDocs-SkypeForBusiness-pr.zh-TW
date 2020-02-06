---
title: 裝置設定 [建立新的] 或 [編輯現有]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 [新增裝置設定] 或 [編輯裝置設定] 頁面上，您可以建立或修改用來管理商務用 Skype Phone Edition 的設定集合。 這些設定讓您可設定諸如必要的安全性模式、裝置記錄層次、語音服務品質 (QoS) 設定，以及電話是否應該在沒有任何活動的指定期間過後自動鎖定。
ms.openlocfilehash: 95ce62b5d3505e10049d61ead77ce79ee7f2f51b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822926"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>裝置設定：建立新的或編輯現有
 
在 [**新增裝置**設定] 或 [**編輯裝置**設定] 頁面上，您可以建立或修改用來管理商務用 Skype Phone Edition 的設定集合。 這些設定讓您可設定諸如必要的安全性模式、裝置記錄層次、語音服務品質 (QoS) 設定，以及電話是否應該在沒有任何活動的指定期間過後自動鎖定。
  
## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可在「新增裝置設定」**** 或「編輯裝置設定」**** 頁面上執行下列工作：
  
- 新增裝置設定。
    
- 修改現有裝置設定的屬性。
    
## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。
  
- **範圍**識別裝置設定的範圍（全域或網站）。
    
- **名稱**您可以新增或修改裝置配置的名稱。
    
- **SIP 安全性**您可以設定商務用 Skype Phone Edition 裝置的傳輸與驗證需求。 您可以從下列選項中選取：
    
  - **低**允許任何類型的授權或傳輸。
    
  - **中型**需要 NTLM 或 Kerberos 才能進行使用者驗證。
    
  - **高**需要 NTLM 或 Kerberos 才能進行使用者驗證，而在 SIP 連線中則需要 TLS。
    
- **記錄層級**您可以在 UC 裝置上啟用記錄功能。 有效值為： Off;低溫深淺[高]。 預設值為 [關閉]。
    
- **語音服務品質（QoS）** 您可以從商務用 Skype Phone Edition 裝置，指定指派給語音流量 emanating 的 DSCP 值。 預設值為40。 不過，40不是通常用於音訊流量的值;相反地，音訊流量幾乎總是以 DSCP 代碼46標示。 為了維持整個網路的一致性，您可能會想要將這個值變更為46。
    
- **電話鎖定**您可以指定 UC 手機是否會在指定的不活動期後自動鎖定本身。 以下是您可以設定的設定：
    
  - **強制執行裝置鎖定**您可以選取此核取方塊來強制執行裝置鎖定。
    
  - **最小 PIN 長度**您可以為用來解除鎖定電話的個人識別碼（PIN）指定最小長度。 PIN 長度的範圍是四到15位數。 預設長度是6個數字。
    
  - **電話封鎖超時**您可以指定電話鎖定本身之前的最短時間長度。 超時的範圍是0到60分鐘;預設值為10分鐘。 以 HH： MM： SS 格式輸入值。
    
## <a name="see-also"></a>另請參閱

[裝置組態](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
