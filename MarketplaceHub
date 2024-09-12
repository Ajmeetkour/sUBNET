// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract MarketplaceHub {
    struct Offer {
        address vendor;
        address item;
        uint256 cost;
        bool isPurchased;
        uint256 postedAt;
    }

    uint256 public offerCount;
    mapping(uint256 => Offer) public offers;
    mapping(address => uint256[]) public vendorOffers;

    event NewOffer(uint256 indexed offerId, address indexed vendor, address item, uint256 cost);
    event PurchaseCompleted(uint256 indexed offerId, address indexed buyer);
    event OfferRemoved(uint256 indexed offerId, address indexed vendor);

    function postOffer(address _item, uint256 _cost) external {
        require(_cost > 0, "Cost must be greater than 0");
        offerCount += 1;
        offers[offerCount] = Offer(msg.sender, _item, _cost, false, block.timestamp);
        vendorOffers[msg.sender].push(offerCount);
        emit NewOffer(offerCount, msg.sender, _item, _cost);
    }

    function purchase(uint256 _offerId) external payable {
        Offer storage offer = offers[_offerId];
        require(!offer.isPurchased, "Offer already purchased");
        require(msg.value >= offer.cost, "Insufficient payment");

        offer.isPurchased = true;
        payable(offer.vendor).transfer(offer.cost);

        if (msg.value > offer.cost) {
            // Refund the excess amount
            payable(msg.sender).transfer(msg.value - offer.cost);
        }

        emit PurchaseCompleted(_offerId, msg.sender);
    }

    function getOffer(uint256 _offerId) external view returns (Offer memory) {
        return offers[_offerId];
    }

    function removeOffer(uint256 _offerId) external {
        Offer storage offer = offers[_offerId];
        require(offer.vendor == msg.sender, "Only the vendor can remove the offer");
        require(!offer.isPurchased, "Offer already purchased");

        delete offers[_offerId];
        for (uint256 i = 0; i < vendorOffers[msg.sender].length; i++) {
            if (vendorOffers[msg.sender][i] == _offerId) {
                vendorOffers[msg.sender][i] = vendorOffers[msg.sender][vendorOffers[msg.sender].length - 1];
                vendorOffers[msg.sender].pop();
                break;
            }
        }

        emit OfferRemoved(_offerId, msg.sender);
    }

    function getVendorOffers(address _vendor) external view  {
        vendorOffers[_vendor];
    }

    function getLatestOffers(uint256 _count) external view returns (Offer[] memory) {
        Offer[] memory latestOffers = new Offer[](_count);
        uint256 count = 0;
        for (uint256 i = offerCount; i > 0 && count < _count; i--) {
            if (!offers[i].isPurchased) {
                latestOffers[count] = offers[i];
                count++;
            }
        }
        return latestOffers;
    }
}
