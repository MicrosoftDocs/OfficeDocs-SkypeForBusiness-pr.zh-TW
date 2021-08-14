---
title: 啟用或停用匿名使用者存取
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何在商務用 Skype Server 中啟用和停用匿名使用者存取。
ms.openlocfilehash: 4f7fb11e7b168922a4027e75703c164638dd1f2d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234388"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的匿名使用者存取

匿名使用者是指沒有組織的 Active Directory 網域服務或支援的同盟網域中的使用者帳戶的使用者，但可邀請他們在內部部署會議中遠端參與。 透過允許匿名參與會議，您可以啟用匿名使用者 (也就是說，其身分識別透過會議或會議金鑰驗證的使用者，只) 加入會議。 允許匿名參與必須為您的組織啟用它。

如果您稍後想要暫時或永久禁止匿名使用者進行存取，您可以對組織停用。 使用本節中的程式來啟用或停用組織的匿名使用者存取。

> [!NOTE]  
> 透過為您的組織啟用匿名使用者存取，您只會指定執行 Access Edge service 的伺服器支援匿名使用者的存取。 除非您也至少要設定一個會議原則，並將其套用至一或多個使用者或使用者群組，否則匿名使用者無法參與您組織中的任何會議。 只有被指派為支援匿名使用者之會議原則的使用者，才可邀請匿名使用者加入會議的使用者。 如需設定會議原則以支援邀請匿名使用者的詳細資訊，請參閱 [管理會議原則](../../conferencing/conferencing-policies.md)。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>啟用或停用組織的匿名使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge** 設定] 中，執行下列其中一項操作：
    
      - 若要為您的組織啟用匿名使用者存取，請選取 [ **啟用與匿名使用者的通訊** ] 核取方塊。
    
      - 若要停用組織的匿名使用者存取，請清除 [ **啟用與匿名使用者的通訊** ] 核取方塊。

6.  按一下 **[認可]**。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用匿名使用者存取

您可以使用 Windows PowerShell 和 **Set-CsAccessEdgeConfiguration** Cmdlet 來管理匿名使用者存取。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 

## <a name="to-enable-anonymous-user-access"></a>啟用匿名使用者存取

  - 若要啟用匿名使用者存取，請將 **AllowAnonymousUsers** 屬性的值設為 True ($True) ：<br/><br/>Set-CsAccessEdgeConfiguration-AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>停用匿名使用者存取

  - 若要停用匿名使用者存取，請將 **AllowAnonymousUsers** 屬性值設為 False ($False) ：<br/><br/>Set-CsAccessEdgeConfiguration-AllowAnonymousUsers $False


## <a name="see-also"></a>另請參閱

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
