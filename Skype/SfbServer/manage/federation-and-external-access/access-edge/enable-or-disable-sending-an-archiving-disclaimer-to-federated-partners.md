---
title: 啟用或停用傳送封存免責聲明至同盟合作夥伴的功能
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: ''
ms.openlocfilehash: 889716377f89e2657adcd6e32c9077b8124e20c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818354"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用聯盟夥伴傳送封存免責聲明

在您部署您的 Edge 伺服器並為貴組織啟用同盟後，您應該已指定是否要將封存免責聲明自動傳送給聯盟夥伴。 如果您封存外部通訊，您應該啟用傳送封存免責聲明。 使用本主題中的程式來變更該設定。

> [!NOTE]
> 下列程式假設您已經為您的組織啟用同盟。 如需啟用同盟的詳細資料，請參閱[啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>啟用或停用將封存免責聲明傳送給聯盟夥伴

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊，以啟用或停用自動傳送封存免責聲明。

6.  按一下 [認可]****。

若要讓聯盟使用者在商務用 Skype Server 部署中與使用者共同作業，您必須至少已將一個外部存取原則設定為支援同盟使用者存取。 如需控制特定聯盟網域存取權的詳細資料，請參閱[設定允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用封存放棄免責聲明

您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理存檔免責聲明的使用。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

## <a name="to-enable-the-archiving-disclaimer"></a>啟用封存放棄免責聲明

  - 若要啟用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 True （$True）：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>停用封存放棄免責聲明

  - 若要停用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


