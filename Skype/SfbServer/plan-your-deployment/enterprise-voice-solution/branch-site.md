---
title: 分支網站 SIP 主幹 in 商務用 Skype Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 瞭解商務用 Skype Server 企業語音中分支網站的 SIP 主幹。
ms.openlocfilehash: b8c1c930bb2500ca9330b14cce7fd5b341db60a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829897"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>分支網站 SIP 主幹 in 商務用 Skype Server
 
瞭解商務用 Skype Server 企業語音中分支網站的 SIP 主幹。
  
在某些情況下，您可能需要在選取的分支網站上執行分散式 SIP 主幹。 若要判斷分支網站是否需要 SIP 主幹，以及在分支網站中部署 sip 主幹時支援的拓撲選項的詳細資訊，請參閱商務用 Skype Server 中的[sip trunk](sip-trunking.md)。
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>分支網站 SIP 主幹需求分析範例

當您決定要部署分支網站 SIP 主幹時，您必須執行網站特定的成本分析。 例如，在華盛頓州的中央網站與位於紐約市的分支網站的企業，應進行分析，以判斷是否要從新的紐約網站執行 SIP 主幹給本機服務提供者。
  
若要判斷紐約的分散式 SIP 主幹是否成本效益，請找出使用 SIP 主幹的「直接向內撥」)  (，並分析紐約的呼叫數目，以撥打 Redmond (425) 以外的區域。 您可以在中央網站上終止分支網站。 例如，Redmond 中央網站可以主控紐約分支網站的數目。 若實施分散式 SIP 主幹的成本低於這些通話的成本，請考慮在紐約分支網站實施 SIP 主幹。 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支網站 SIP 主幹需求

部署 SIP 主幹（而非閘道）的選擇是以公用交換電話網路 (PSTN) 長途電話計費每個選項之間的差異為基礎。 如果您部署分支網站 SIP 主幹，您也需要判斷您的恢復能力和頻寬需求。 如果分支網站與中央網站之間的連結具備彈性，且具有足夠的頻寬，您可以部署 SIP 主幹或閘道。 您不需要在分支網站上部署 Survivable 分支裝置。 如果分支網站與中央網站之間的連結無法復原，請部署 Survivable 分支裝置，或使用分支網站上的閘道或 SIP 主幹來部署 Survivable 分支伺服器。 
  

