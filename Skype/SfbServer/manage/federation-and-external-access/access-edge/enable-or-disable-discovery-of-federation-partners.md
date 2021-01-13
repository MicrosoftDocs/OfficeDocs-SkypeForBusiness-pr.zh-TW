---
title: 啟用或停用同盟協力廠商探索
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: 當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817423"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的同盟合作夥伴探索

當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。 使用本主題中的程式來變更該設定。

> [!NOTE]  
> 下列程式假設您已經為組織啟用同盟。 如需啟用同盟的詳細資訊，請參閱 [啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>啟用或停用組織的自動探索同盟網域

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。

3.  在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge** 設定] 的 [ **啟用與同盟使用者的通訊**] 下，選取或清除 [ **啟用夥伴網域探索** ] 核取方塊，以啟用或停用自動探索夥伴網域。

6.  按一下 **[認可]**。

若要讓同盟使用者與商務用 Skype Server 部署中的使用者共同作業，您必須至少設定一個外部存取原則，以支援同盟使用者存取。 如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md)。 如需控制特定同盟網域存取權的詳細資訊，請參閱 [管理 sip 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 和 [管理 sip 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用同盟協力廠商的探索

同盟協力廠商的探索可使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 


## <a name="to-enable-discovery-of-federation-partners"></a>啟用同盟協力廠商的探索

  - 若要啟用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 True ($True) 。 請注意，您必須啟用 DNS SRV 路由才能變更此屬性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>停用同盟協力廠商的探索

  - 若要停用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 False ($False) ：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

