---
title: 管理組織的外部使用存取原則
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
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
description: 部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818274"
---
# <a name="manage-external-access-policy-for-your-organization"></a>管理組織的外部使用存取原則

部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。

根據預設，沒有任何原則可設定支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。 若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。 下列原則作用中可供建立及設定。 根據預設，會建立全域原則，但無法刪除。

  - **全域原則**   當您部署邊緣伺服器時，就會建立全域原則。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。 全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，就不會將它移除。 相反地，您可以將其重設為預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。 網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。 根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。 使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。 例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。 如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。


> [!IMPORTANT]  
> 在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。


這些選項包括下列外部存取類型：

  - ****    如果您想要支援使用者存取聯盟夥伴網域，請啟用與同盟使用者進行通訊。 此設定會設定使用者與其他 SIP 聯盟網域通訊的能力，以及 Microsoft Office 365 等主機提供者。 


  - ****    如果您想讓組織中的使用者（例如正在旅行的遠端電腦和使用者）能夠透過網際網路連線到商務用 Skype Server，請啟用 [與遠端使用者進行通訊] 選項。

  - ****    如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊，請啟用 [與公用使用者通訊]。
   

> [!NOTE]  
> 除了啟用外部使用者存取支援之外，您也必須先設定原則，以控制在您的組織中使用外部使用者存取權，才能供使用者使用任何類型的外部使用者存取。 如需建立、設定及套用外部使用者存取原則的詳細資料，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。



**使用 Windows PowerShell Cmdlet 來查看外部存取原則**

  - 您可以使用商務用 Skype Server Management 命令介面和**CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 
    
    若要查看所有外部存取原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
    `Get-CsExternalAccessPolicy`
    
    這個命令會傳回如下所示的資訊：
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
