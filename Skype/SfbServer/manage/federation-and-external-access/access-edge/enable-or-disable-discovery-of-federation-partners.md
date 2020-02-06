---
title: 啟用或停用探索同盟協力廠商
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818394"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用同盟合作夥伴的發現功能

當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。 使用本主題中的程式來變更該設定。

> [!NOTE]  
> 下列程式假設您已經為您的組織啟用同盟。 如需啟用同盟的詳細資料，請參閱[啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>若要啟用或停用貴組織的聯盟網域自動探索

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**啟用合作夥伴網域探索**] 核取方塊，以啟用或停用合作夥伴網域的自動探索。

6.  按一下 [認可]****。

若要讓聯盟使用者在商務用 Skype Server 部署中與使用者共同作業，您必須至少已將一個外部存取原則設定為支援同盟使用者存取。 如需詳細資訊，請參閱[啟用或停用同盟與公用 IM](enable-or-disable-federation-and-public-im-connectivity.md)連線。 如需控制特定聯盟網域存取權的詳細資料，請參閱[管理 sip 聯盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 sip 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用同盟合作夥伴的探索

同盟合作夥伴的探索可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 進行管理。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 


## <a name="to-enable-discovery-of-federation-partners"></a>若要啟用同盟合作夥伴的探索

  - 若要啟用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 True （$True）。 請注意，您必須啟用 DNS SRV 路由才能變更這個屬性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>若要停用同盟合作夥伴的探索

  - 若要停用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

