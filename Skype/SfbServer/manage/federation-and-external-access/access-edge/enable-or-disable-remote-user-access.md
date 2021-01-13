---
title: 啟用或停用遠端使用者存取
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: 如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，即可使用商務用 Skype Server 與內部使用者共同作業。
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817393"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用遠端使用者存取

遠端使用者是組織中具有持久 Active Directory 身分識別的使用者。 遠端使用者通常會在您的網路外登入商務用 Skype Server，只要使用虛擬私人網路 (VPN) 未連接到組織的網路。 遠端使用者包括在家中或在旅途中運作的員工，以及其他遠端工作者（如受信任的供應商，其已獲授與企業認證）。 如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，即可使用商務用 Skype Server 與內部使用者共同作業。

若要支援遠端使用者存取，您必須啟用遠端使用者存取。 當您啟用遠端使用者存取時，您可以為整個組織啟用它。 如果您稍後想要暫時或永久防止遠端使用者存取，您可以為組織停用它。 使用本節中的程式來啟用或停用組織的遠端使用者存取。


> [!NOTE]  
> 啟用遠端使用者存取只會指定執行 Access Edge service 的伺服器可支援與遠端使用者的通訊，但遠端使用者無法參與立即訊息 (IM) 或組織中的會議，除非您也設定至少一個原則來管理遠端使用者存取的使用。 在一個原則層級套用的商務用 Skype 伺服器原則設定，可以覆寫在另一個原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。 如需設定使用遠端使用者存取之原則的詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制遠端使用者存取](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>啟用或停用組織的遠端使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **Access Edge** 設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge** 設定] 中，執行下列其中一項操作：
    
      - 若要啟用組織的遠端使用者存取，請選取 [ **啟用遠端使用者存取** ] 核取方塊。
    
      - 若要停用組織的遠端使用者存取，請清除 [ **啟用遠端使用者存取** ] 核取方塊。

6.  按一下 **[認可]**。

若要讓遠端使用者登入執行商務用 Skype 伺服器的伺服器，您也必須至少設定一個外部存取原則，以支援遠端使用者存取。 如需詳細資訊，請參閱 [Configure 原則 to control remote user access In 商務用 Skype Server](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用遠端使用者存取

您可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理遠端使用者存取。 您可以從商務用 Skype Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 

## <a name="to-enable-remote-user-access"></a>啟用遠端使用者存取

  - 若要啟用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 True ($True) ：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>停用遠端使用者存取

  - 若要停用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 False ($False) ：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


