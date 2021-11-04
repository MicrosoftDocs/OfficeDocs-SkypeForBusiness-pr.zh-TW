---
title: 管理組織的外部存取原則
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。
ms.openlocfilehash: d2e7e19e461e0b7777969aac4a73a50bb683e69c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763711"
---
# <a name="manage-external-access-policy-for-your-organization"></a>管理組織的外部存取原則

部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。

依預設，不會將任何原則設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已經為組織啟用外部使用者存取支援也一樣。若要控制外部使用者存取的使用，您必須設定一或多個原則，並為每個原則指定支援的外部使用者存取類型。您可以使用下列原則範圍來進行建立和設定。預設會建立全域原則，但無法加以刪除。

  - **全域原則**   全域原則是在您部署 Edge Server 時所建立。依預設，全域原則中不會啟用任何外部使用者存取選項。若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個外部使用者存取選項類型。全域原則會套用至組織內所有使用者，但網站原則和使用者原則優先於全域原則。如果刪除全域原則，並不代表將其移除，而是將其重設為預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以對特定網站限制外部使用者存取支援。網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立並設定個或多個使用者原則，以對特定使用者限制遠端使用者存取支援。使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。


> [!IMPORTANT]  
> 在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。


這些選項包括下列類型的外部存取：

  - **啟用與同盟使用者的通訊**   如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。 此設定會設定使用者與其他 SIP 同盟網域通訊的能力，以及主控的提供者，如 Microsoft 365 或 Office 365。 


  - **啟用與遠端使用者的通訊**  如果您想要組織中的使用者（例如出差的遠端辦公和使用者）可以透過網際網路連線至商務用 Skype Server，請啟用此選項。

  - **啟用與公用使用者的通訊**   如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊，請啟用此選項。
   

> [!NOTE]  
> 除了啟用外部使用者存取支援，您還必須設定相關原則以控制組織外部使用者存取的使用，接著再為使用者提供任何類型的外部使用者存取。 如需有關建立、設定及套用外部使用者存取原則的詳細資訊，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。



**使用 Windows PowerShell Cmdlet 來檢視外部存取原則**

  - 您可以使用商務用 Skype Server 管理命令介面和 **CsExternalAccessPolicy** Cmdlet 來檢視外部存取原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 
    
    若要檢視關於您所有外部存取原則的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
    `Get-CsExternalAccessPolicy`
    
    此命令會傳回與下列相似的資訊：
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
