---
title: 主幹設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要編輯或修改 SIP 主幹的設定，請執行下列動作：
ms.openlocfilehash: 5859686a6fedf8c4da15ada5c4ad92f47c24b756
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114139"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="0ab01-103">主幹設定展開工具</span><span class="sxs-lookup"><span data-stu-id="0ab01-103">Trunk Settings Expander</span></span>

<span data-ttu-id="0ab01-104">若要編輯或修改 SIP 主幹的設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0ab01-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="0ab01-105">[主幹名稱] 是唯一識別部署中 SIP 主幹的必要項目。</span><span class="sxs-lookup"><span data-stu-id="0ab01-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="0ab01-106">**關聯的 PSTN 閘道**：選取部署中已定義的現有 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0ab01-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="0ab01-p101">**IP/PSTN 閘道的聆聽連接埠**：指出閘道將在哪個 TCP/IP 連接埠聆聽要求。所需的值可能依閘道的廠商而異，但預設值是連接埠 5067。</span><span class="sxs-lookup"><span data-stu-id="0ab01-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="0ab01-p102">**SIP 傳輸通訊協定**：使用通訊協定 TCP 或 TLS。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。</span><span class="sxs-lookup"><span data-stu-id="0ab01-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="0ab01-113">**關聯** 的轉送伺服器：從部署選取現有的轉送伺服器，以與 SIP 主幹產生關聯。</span><span class="sxs-lookup"><span data-stu-id="0ab01-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab01-114">只有根主幹可以與 Lync Server 2010 或 Lync Server 2013 轉送伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="0ab01-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="0ab01-115">**關聯的轉送伺服器埠**：必要值，此值會設定為轉送伺服器設定為接聽的值。</span><span class="sxs-lookup"><span data-stu-id="0ab01-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![主幹設定展開工具](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="0ab01-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ab01-117">See also</span></span>

[<span data-ttu-id="0ab01-118">SIP 主幹部署檢查表</span><span class="sxs-lookup"><span data-stu-id="0ab01-118">SIP Trunking Deployment Checklist</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[<span data-ttu-id="0ab01-119">SIP 主幹的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="0ab01-119">Components and Topologies for SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)