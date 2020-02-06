---
title: 主幹設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要編輯或修改 SIP 主幹的設定，請執行下列動作：
ms.openlocfilehash: aa3c8dd622e64bcd063e84d1f6e19278af9a6cff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819145"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="3fc6d-103">主幹設定展開工具</span><span class="sxs-lookup"><span data-stu-id="3fc6d-103">Trunk Settings Expander</span></span>

<span data-ttu-id="3fc6d-104">若要編輯或修改 SIP 主幹的設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3fc6d-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="3fc6d-105">[主幹名稱]\*\*\*\* 是唯一識別部署中 SIP 主幹的必要項目。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="3fc6d-106">**關聯的 PSTN 閘道**：選取部署中已定義的現有 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="3fc6d-p101">**IP/PSTN 閘道的聆聽連接埠**：指出閘道將在哪個 TCP/IP 連接埠聆聽要求。所需的值可能依閘道的廠商而異，但預設值是連接埠 5067。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="3fc6d-p102">**SIP 傳輸通訊協定**：使用通訊協定 TCP 或 TLS。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="3fc6d-113">**關聯的中繼伺服器**：從部署選取現有的中繼伺服器，以與 SIP 幹線建立關聯。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="3fc6d-114">只有根幹線可以與 Lync Server 2010 或 Lync Server 2013 轉送伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="3fc6d-115">**關聯的中繼伺服器埠**： [必要] 值，會設定為轉送伺服器設定為要偵聽的值。</span><span class="sxs-lookup"><span data-stu-id="3fc6d-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![主幹設定展開工具](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="3fc6d-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3fc6d-117">See also</span></span>

[<span data-ttu-id="3fc6d-118">SIP 中繼部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3fc6d-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="3fc6d-119">SIP 中繼的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="3fc6d-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
