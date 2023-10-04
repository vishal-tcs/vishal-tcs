<?xml version="1.0" encoding="utf-8"?>
<!-- edited with XMLSpy v2013 rel. 2 sp2 (x64) (http://www.altova.com) by ﻿AMADEUS s.a.s. (AMADEUS s.a.s.) -->
<xs:schema xmlns="http://xml.amadeus.com/2010/06/REV_v1" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:iata_ct="http://www.iata.org/IATA/2007/00"
targetNamespace="http://xml.amadeus.com/2010/06/REV_v1" elementFormDefault="qualified" version="3.7.2">
    <xs:import namespace="http://www.iata.org/IATA/2007/00" schemaLocation="../iata_ct/IATA_ET_CommonTypes.xsd" />
    <xs:include schemaLocation="REV_CommonTypes.xsd" />
    <xs:complexType name="Transaction">
        <xs:sequence minOccurs="0">
            <xs:element name="Event">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="EventNumber" type="xs:integer" />
                        <xs:element name="EventVersion" type="xs:integer" />
                        <xs:element name="EventType" type="xs:string" minOccurs="0" />
                        <xs:element name="Event" type="xs:dateTime" minOccurs="0" />
                        <xs:element name="EntityStatus" type="EntityStatus" minOccurs="0" />
                        <xs:element name="EventTypeShortCode" type="xs:string" minOccurs="0" />
                        <xs:element name="JournalDate" type="xs:date" minOccurs="0" />
                        <xs:element name="WithUpdatedAccountedDate" type="xs:string" default="N" minOccurs="0" />
                        <xs:element name="ParentEventNumber" type="xs:integer" minOccurs="0" />
                        <xs:element name="CreatedBy" type="xs:string" minOccurs="0" />
                        <xs:element name="OfficeId" type="xs:string" minOccurs="0" />
                        <xs:element name="Usecase" minOccurs="0" maxOccurs="unbounded">
                            <xs:complexType>
                                <xs:sequence minOccurs="0">
                                    <xs:element name="UsecaseType" type="xs:string" minOccurs="0" />
                                    <xs:element name="FCSRemark" type="xs:string" minOccurs="0" />
                                    <xs:element name="ModifiedEntities" minOccurs="0" maxOccurs="unbounded">
                                        <xs:complexType>
                                            <xs:sequence minOccurs="0">
                                                <xs:element name="Action" minOccurs="0" maxOccurs="unbounded">
                                                    <xs:complexType>
                                                        <xs:sequence minOccurs="0">
                                                            <xs:element name="SubAction" minOccurs="0" maxOccurs="unbounded">
                                                                <xs:complexType>
                                                                    <xs:attribute name="Description" type="xs:string" />
                                                                </xs:complexType>
                                                            </xs:element>
                                                        </xs:sequence>
                                                        <xs:attribute name="Actor" type="xs:string" />
                                                        <xs:attribute name="ActionDetail" type="xs:string" />
                                                    </xs:complexType>
                                                </xs:element>
                                            </xs:sequence>
                                            <xs:attribute name="ElementType" type="xs:string" />
                                            <xs:attribute name="ElementID" type="xs:integer" />
                                        </xs:complexType>
                                    </xs:element>
                                </xs:sequence>
                            </xs:complexType>
                        </xs:element>
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
            <xs:choice minOccurs="0">
                <xs:element name="Document" minOccurs="0">
                    <xs:complexType>
                        <xs:sequence minOccurs="0">
                            <xs:element name="IssuanceDetails" type="IssuerInformation_REV" minOccurs="0" />
                            <xs:element name="BookingInformation" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="PNRIdentification" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AmadeusRecordLocator" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="CompanyCode" type="xs:string" minOccurs="0" />
                                                                <xs:element name="ID" type="xs:string" minOccurs="0" />
                                                                <xs:element name="CreationDate" type="xs:date" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="OriginalRecordLocator" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="CompanyCode" type="xs:string" minOccurs="0" />
                                                                <xs:element name="ID" type="xs:string" minOccurs="0" />
                                                                <xs:element name="CreationDate" type="xs:date" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="BookingAgencyDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="IataNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OfficeId" type="xs:string" minOccurs="0" />
                                                    <xs:element name="AgentSine" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OfficeCityCode" type="xs:string" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="IssuedInExchangeFor" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="PrimaryDocumentNbr" type="xs:string" minOccurs="0" />
                                        <xs:element name="IssuanceLocalDate" type="xs:date" minOccurs="0" />
                                        <xs:element name="ExchangedCoupons" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:attribute name="ConjunctiveCouponNbr" type="xs:integer" use="optional" />
                                                <xs:attribute name="ConjunctiveDocumentNbr" type="xs:string" use="optional" />
                                                <xs:attribute name="Status" type="xs:string" use="optional" />
                                                <xs:attribute name="InvoluntaryIndicator" type="xs:string" use="optional" />
                                                <xs:attribute name="SACCode" type="xs:string" use="optional" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FOP" type="FOP_REV" minOccurs="0" maxOccurs="unbounded" />
										<xs:element name="PatchedCoupons" type="PatchedCoupons_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="OriginalIssueInfo" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:attribute name="PrimaryDocumentNbr" type="xs:string" />
                                    <xs:attribute name="IssuanceLocalDate" type="xs:date" use="optional" />
                                    <xs:attribute name="IataNumber" type="xs:string" use="optional" />
                                    <xs:attribute name="CityCode" type="xs:string" use="optional" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="PassengerInformation" minOccurs="0">
                                <xs:complexType>
                                    <xs:attribute name="Surname" type="xs:string" />
                                    <xs:attribute name="FirstName" type="xs:string" />
                                    <xs:attribute name="PassengerTypeCode" type="xs:string" />
                                    <xs:attribute name="FarePassengerTypeCode" type="xs:string" use="optional" />
                                    <xs:attribute name="StaffNumber" type="xs:string" use="optional" />
                                    <xs:attribute name="StaffDateOfJoining" type="xs:date" use="optional" />
                                    <xs:attribute name="DateOfBirth" type="xs:date" use="optional" />
                                    <xs:attribute name="IsStaff" type="xs:string" default="N" />
                                    <xs:attribute name="StaffCostCenter" type="xs:string" />
                                    <xs:attribute name="CustomerFileRef" type="xs:string" />
                                    <xs:attribute name="PaxSpecificData" type="xs:string" />
                                    <xs:attribute name="IdCardNumber" type="xs:string" use="optional" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="ItineraryDetails" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="RoutingType" type="xs:string" minOccurs="0" />
                                        <xs:element name="OneWayIndicator" type="xs:string" default="N" minOccurs="0" />
                                        <xs:element name="FinalDestination" type="xs:string" minOccurs="0" />
                                        <xs:element name="TODC" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="OriginCityCode" type="xs:string" minOccurs="0" />
					       <xs:element name="OriginCityCodeRealItinerary" type="xs:string" minOccurs="0" />
                                                    <xs:element name="DestinationCityCode" type="xs:string" minOccurs="0" />
					       <xs:element name="DestinationCityCodeRealItinerary" type="xs:string" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="AgencyMemoInformation" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="ReasonForMemoInformation" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="ReasonForMemoCode" type="xs:string" minOccurs="0" />
                                                    <xs:element name="ReasonForMemoText" type="xs:string" minOccurs="0" />
                                                    <xs:element name="ReasonFullComment" type="xs:string" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                    <xs:attribute name="MemoType" type="xs:string" use="optional" />
                                    <xs:attribute name="MemoNumber" type="xs:string" use="optional" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="PricingDetails" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="IsRevenuePassenger" type="xs:string" minOccurs="0" />
                                        <xs:element name="TourCode" type="xs:string" minOccurs="0" />
                                        <xs:element name="IsITBT" type="xs:string" minOccurs="0" />
                                        <xs:element name="FareCalculation" type="xs:string" minOccurs="0" />
                                        <xs:element name="FCMI" type="xs:string" minOccurs="0" />
                                        <xs:element name="IsNetRemit" type="xs:string" minOccurs="0" />
                                        <xs:element name="EndorsementText" type="xs:string" minOccurs="0" />
                                        <xs:element name="NonEndorsableInd" type="xs:string" minOccurs="0" />
                                        <xs:element name="CurrencyOfPayment" type="xs:string" minOccurs="0" />
                                        <xs:element name="FCPI" type="xs:string" minOccurs="0" />
                                        <xs:element name="FareDescription" type="xs:string" minOccurs="0" />
                                        <xs:element name="PFWeightedRevenue" type="xs:float" minOccurs="0" />
                                        <xs:element name="TPMWeightedRevenue" type="xs:float" minOccurs="0" />
                                        <xs:element name="TPMSum" type="xs:integer" minOccurs="0" />
                                        <xs:element name="ProrateFactorSum" type="xs:integer" minOccurs="0" />
                                        <xs:element name="AREI" type="xs:string" minOccurs="0" />
                                        <xs:element name="CARF" type="xs:string" minOccurs="0" />
                                        <xs:element name="RemittanceAmount" type="AccountableEntity_REV" minOccurs="0" />
                                        <xs:element name="TotalDocumentAmount" type="AccountableEntity_REV" minOccurs="0" />
                                        <xs:element name="RevenueAttributableAgent" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attribute name="AgencyNumber" type="xs:string" />
                                                <xs:attribute name="CityCode" type="xs:string" />
                                                <xs:attribute name="AgencyType" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FareComponent" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RelatedCoupon" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:attribute name="CouponNumber" type="xs:integer" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="SSPFareInformation" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="PassengerTypeCode" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:attribute name="Code" type="xs:string" />
                                                                        <xs:attribute name="DiscountPercentage" type="xs:decimal" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                            <xs:attribute name="FareOwner" type="xs:string" />
                                                            <xs:attribute name="IATAFareCategory" type="xs:string" />
                                                            <xs:attribute name="ATPCOFareCategory" type="xs:string" />
                                                            <xs:attribute name="FareClass" type="xs:string" />
                                                            <xs:attribute name="FareTypeCode" type="xs:string" />
                                                            <xs:attribute name="SeasonalCode" type="xs:string" />
                                                            <xs:attribute name="PartOfTheWeek" type="xs:string" />
                                                            <xs:attribute name="PartOfTheDay" type="xs:string" />
                                                            <xs:attribute name="FarePublishingType" type="xs:string" />
                                                            <xs:attribute name="RoutingType" type="xs:string" />
                                                            <xs:attribute name="SectorFareIndicator" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ABRFareInformation" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="PassengerTypeCode" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:attribute name="Code" type="xs:string" />
                                                                        <xs:attribute name="DiscountPercentage" type="xs:decimal" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                            <xs:attribute name="FareCategory" type="xs:string" />
                                                            <xs:attribute name="FareClass" type="xs:string" />
                                                            <xs:attribute name="FareTypeCode" type="xs:string" />
                                                            <xs:attribute name="SeasonalCode" type="xs:string" />
                                                            <xs:attribute name="PartOfTheWeek" type="xs:string" />
                                                            <xs:attribute name="PartOfTheDay" type="xs:string" />
                                                            <xs:attribute name="FarePublishingType" type="xs:string" />
                                                            <xs:attribute name="FFPAward" type="xs:string" />
                                                            <xs:attribute name="ZEDFareLevel" type="xs:string" />
                                                            <xs:attribute name="SpecialFareBasisIndicator" type="xs:string" />
                                                            <xs:attribute name="NonRevenuePassengerIndicator" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RAFareInformation" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="PassengerTypeCode" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:attribute name="Code" type="xs:string" />
                                                                        <xs:attribute name="DiscountPercentage" type="xs:decimal" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                            <xs:attribute name="FareOwner" type="xs:string" />
                                                            <xs:attribute name="FareCategory" type="xs:string" />
                                                            <xs:attribute name="FareClass" type="xs:string" />
                                                            <xs:attribute name="FareTypeCode" type="xs:string" />
                                                            <xs:attribute name="SeasonalCode" type="xs:string" />
                                                            <xs:attribute name="PartOfTheWeek" type="xs:string" />
                                                            <xs:attribute name="PartOfTheDay" type="xs:string" />
                                                            <xs:attribute name="FarePublishingType" type="xs:string" />
                                                            <xs:attribute name="RoutingType" type="xs:string" />
                                                            <xs:attribute name="SectorFareIndicator" type="xs:string" />
                                                            <xs:attribute name="FFPAward" type="xs:string" />
                                                            <xs:attribute name="ZEDFareLevel" type="xs:string" />
                                                            <xs:attribute name="SpecialFareBasisIndicator" type="xs:string" />
                                                            <xs:attribute name="NonRevenuePassengerIndicator" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
													<xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="FareComponentNumber" type="xs:integer" />
												<xs:attribute name="FareComponentOrigin" type="xs:string" />
												<xs:attribute name="FareComponentDestination" type="xs:string" />
												<xs:attribute name="FareComponentAmount" type="xs:decimal" />
												<xs:attribute name="FareComponentCurrency" type="xs:string" />
												<xs:attribute name="PointOfTurnaround" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TKMI" type="xs:string" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="Fares" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Fare" type="Fare_REV" minOccurs="0" maxOccurs="unbounded" />
										<xs:element name="LafFare" type="Fare_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
							<xs:element name="Penalties" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Penalty" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="FopInformation" type="FOP_REV" minOccurs="0" maxOccurs="unbounded" />
                            <xs:element name="StandardCommission" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Commission" type="Commission_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="StandardCommissionTransferred" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="SupplementaryCommission" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Commission" type="Commission_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="SupplementaryCommissionTransferred" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
							<xs:element name="CreditCardTransferredCommission" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="EffectiveCommission" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Commission" type="Commission_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="Taxes" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="CollectedTaxes" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="Tax" type="Tax_REV" minOccurs="0" maxOccurs="unbounded" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CollectedTaxesDocLvl" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="Tax" type="Tax_REV" minOccurs="0" maxOccurs="unbounded" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="RemittanceTaxesDocLvl" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RemittanceTaxDocLvl" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Tax" type="Tax_REV" minOccurs="0" />
                                                                <xs:element name="RemittanceTaxCalculatedValues" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="AccountableEntity" type="AccountableEntity_REV"
                                                                            minOccurs="0" />
                                                                            <xs:element name="TaxJustification" type="TaxJustification_REV" minOccurs="0" maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                        <xs:attribute name="CalculationSource" type="xs:string" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="TaxHandlingFee" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="AccountableEntity" type="AccountableEntity_REV"
                                                                            minOccurs="0" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="TaxOnCommission" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Tax" type="VAT_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="Fees" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="Fee" type="Fee_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
							<xs:element name="TransferredFees" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="TransferredFee" type="Fee_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
							<xs:element name="TransferredEMDSFees" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="TransferredEMDSFee" minOccurs="0" maxOccurs="unbounded">
											<xs:complexType>
												<xs:sequence minOccurs="0">
													<xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
												</xs:sequence>
												<xs:attribute name="EMDDocumentNumber" type="xs:string" use="optional" />
                                                <xs:attribute name="EMDIssuanceDate" type="xs:date" use="optional" />
                                                <xs:attribute name="EMDReasonForIssuanceCode" type="xs:string" use="optional" />
                                                <xs:attribute name="EMDReasonForIssuanceSubCode" type="xs:string" use="optional" />
											</xs:complexType>
										</xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="ReportingInformation" type="ReportingInformation_REV" minOccurs="0" />
							<xs:element name="GSTBusinessInformation" type="GSTBusinessInformation_REV" minOccurs="0" />
							<xs:element name="FareCalculationNonProratedAmount" type="FareCalculationNonProratedAmount_REV" minOccurs="0" maxOccurs="unbounded" />
                            <xs:element name="Coupon" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="FrequentFlyerDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attribute name="ProgramID" type="xs:string" use="optional" />
                                                <xs:attribute name="MembershipID" type="xs:string" use="optional" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="SegmentInfo" type="SegmentInfo_REV" minOccurs="0" />
                                        <xs:element name="CouponDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="SAC" type="xs:string" minOccurs="0" />
                                                    <xs:element name="FareBasisCode" type="xs:string" minOccurs="0" />
                                                    <xs:element name="NewTicketInformation" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExchangedToDocumentNbr" type="xs:string" minOccurs="0" />
                                                                <xs:element name="NewIssLocalDate" type="xs:date" minOccurs="0" />
                                                                <xs:element name="NewValidatingCode" type="xs:string"
                                                                minOccurs="0" />
                                                                <xs:element name="NewTicketType" type="xs:string" minOccurs="0" />
                                                                <xs:element name="ExchangeEventNumber" type="xs:integer" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="AssociatedCoupons" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="CouponNbr" type="xs:integer" minOccurs="0" />
                                                                <xs:element name="PrimaryDocumentNbr" type="xs:string" minOccurs="0" />
                                                                <xs:element name="OriginalIssuanceDate" type="xs:date" minOccurs="0" />
                                                                <xs:element name="IsDissociated" type="xs:string" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CalculatedAmounts" type="CouponAmounts_REV" minOccurs="0" />
										<xs:element name="EMDSFeeCouponLevel" minOccurs="0" maxOccurs="unbounded">
											<xs:complexType>
												<xs:sequence minOccurs="0">
													<xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
												</xs:sequence>
												<xs:attribute name="EMDDocumentNumber" type="xs:string" use="optional" />
                                                <xs:attribute name="EMDIssuanceDate" type="xs:date" use="optional" />
                                                <xs:attribute name="EMDReasonForIssuanceCode" type="xs:string" use="optional" />
                                                <xs:attribute name="EMDReasonForIssuanceSubCode" type="xs:string" use="optional" />
											</xs:complexType>
										</xs:element>
                                        <xs:element name="ProrationDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="TicketedPointMileage" type="xs:nonNegativeInteger" minOccurs="0" />
                                                    <xs:element name="ProrateFactor" type="xs:nonNegativeInteger" minOccurs="0" />
                                                    <xs:element name="ProratedValues" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ProratedValue" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="AccountableEntity" type="AccountableEntity_REV"
                                                                            minOccurs="0" />
                                                                        </xs:sequence>
                                                                        <xs:attribute name="ProrationSource" type="xs:string" />
                                                                        <xs:attribute name="ProrationCode" type="xs:string" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="InterlineDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="InterlineInformation" type="InterlineInformation_REV" minOccurs="0" />
                                                    <xs:element name="OriginalInterlineInformation" type="InterlineInformation_REV" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="BaggageAllowance" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RatePerUnit" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Amount" type="Amount_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                                <xs:attribute name="Quantity" type="xs:string" />
                                                <xs:attribute name="Weight" type="xs:decimal" />
                                                <xs:attribute name="WeightUnit" type="xs:string" />
                                                <xs:attribute name="SeatUsedForBaggage" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="RequestResponseDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AllianceInformation" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attribute name="RequestSentStatus" type="xs:string" />
                                                            <xs:attribute name="ResponseReceivedStatus" type="xs:string" />
                                                            <xs:attribute name="RequestReceivedStatus" type="xs:string" />
                                                            <xs:attribute name="ResponseSentStatus" type="xs:string" />
                                                            <xs:attribute name="PartnerAirline" type="xs:string" />
                                                            <xs:attribute name="LevelType" type="xs:integer" />
                                                            <xs:attribute name="LevelSubtype" type="xs:string" />
                                                            <xs:attribute name="ESALFileType" type="xs:string" />
                                                            <xs:attribute name="ESALFileName" type="xs:string" />
                                                            <xs:attribute name="ESALFileDate" type="xs:date" />
                                                            <xs:attribute name="ESALAdjustmentType" type="xs:string" />
                                                            <xs:attribute name="ESALStatus" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RequestResponseCoupon" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="CouponProratedFare" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="AccountableEntity" type="AccountableEntity_REV"
                                                                            minOccurs="0" />
                                                                        </xs:sequence>
                                                                        <xs:attribute name="ProrationSource" type="xs:string" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="CouponStandardCommission" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="Commission" type="Commission_REV" minOccurs="0" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="CouponSuppCommission" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="Commission" type="Commission_REV" minOccurs="0" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                            <xs:attribute name="ResponseAirline" type="xs:string" />
                                                            <xs:attribute name="ResponseFileType" type="xs:string" />
                                                            <xs:attribute name="ResponseFileName" type="xs:string" />
                                                            <xs:attribute name="ResponseFileDate" type="xs:date" />
                                                            <xs:attribute name="ResponseBatchNumber" type="xs:integer" />
						                                    <xs:attribute name="LevelType" type="xs:integer" use="optional" />
                                                            <xs:attribute name="LevelSubtype" type="xs:string" use="optional" />
                                                            <xs:attribute name="MultiCouponID" type="xs:string" />
                                                            <xs:attribute name="IsValidResponseIndicator" type="xs:string" />
                                                            <xs:attribute name="SaleDate" type="xs:date" />
                                                            <xs:attribute name="DealNumber" type="xs:string" use="optional" />
                                                            <xs:attribute name="TourCode" type="xs:string" />
                                                            <xs:attribute name="CreditCardNumber" type="xs:string" use="optional" />
                                                            <xs:attribute name="AgentCode" type="xs:string" />
                                                            <xs:attribute name="AgentCodeCheckDigit" type="xs:string" />
                                                            <xs:attribute name="PNRReferenceNumber" type="xs:string" />
                                                            <xs:attribute name="OriginStationCode" type="xs:string" />
                                                            <xs:attribute name="DestinationStationCode" type="xs:string" />
                                                            <xs:attribute name="TurnaroundStationCode" type="xs:string" />
                                                            <xs:attribute name="PassengerName" type="xs:string" />
                                                            <xs:attribute name="IssuingAgentCode" type="xs:string" />
                                                            <xs:attribute name="IssuingAgentCheckDigit" type="xs:integer" />
                                                            <xs:attribute name="NetRemitIndicator" type="xs:string" />
                                                            <xs:attribute name="CorporateClientIdentification" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RequestInformation" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:attribute name="RequestAirline" type="xs:string" />
                                                            <xs:attribute name="RequestFileType" type="xs:string" />
                                                            <xs:attribute name="RequestFileName" type="xs:string" />
                                                            <xs:attribute name="RequestFileDate" type="xs:date" />
                                                            <xs:attribute name="RequestBatchNumber" type="xs:integer" />
                                                            <xs:attribute name="CouponStatusRequestFile" type="xs:string" />
                                                            <xs:attribute name="MultiCouponID" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="PNRData" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="SSRElement" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:attribute name="Type" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="SKElement" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:attribute name="Type" type="xs:string" />
                                                            <xs:attribute name="FreeText" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                                <xs:attribute name="BookingDateTime" type="xs:dateTime" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="YQYRSurchargeEntity" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="PartnerAirline" type="xs:string" />
                                                <xs:attribute name="ShareYQYRSurchargeInd" type="xs:string" />
                                                <xs:attribute name="YQFileCreationDate" type="xs:date" />
                                                <xs:attribute name="FileName" type="xs:string" />
                                                <xs:attribute name="JourneyType" type="xs:string" />
                                                <xs:attribute name="RemittanceMonth" type="xs:date" />
                                                <xs:attribute name="YQFiletype" type="xs:string" />
                                                <xs:attribute name="YQInwardStatus" type="xs:string" />
                                                <xs:attribute name="JBAAgreementIdentifier" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="ExchangeBalanceCouponLevel" type="AccountableEntity_REV" minOccurs="0" />
                                        <xs:element name="RefundBalanceCouponLevel" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="RefundEventNumber" type="xs:integer" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CouponCodeShareValue" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="CodeShareInvoiceNumber" type="xs:string" />
                                                <xs:attribute name="PaymentDirection" type="xs:string" />
                                                <xs:attribute name="PaymentOwner" type="xs:string" />
                                                <xs:attribute name="BillingPeriod" type="xs:date" />
                                                <xs:attribute name="BillingStatus" type="xs:string" />
                                                <xs:attribute name="IsPayableByFranchise" type="xs:string" />
                                                <xs:attribute name="Percentage" type="xs:decimal" use="optional" />
                                                <xs:attribute name="DifferenceInPercentage" type="xs:decimal" use="optional" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CodeShareUsageFileInfo" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="From" type="xs:string" />
                                                <xs:attribute name="To" type="xs:string" />
                                                <xs:attribute name="BatchNumber" type="xs:string" />
                                                <xs:attribute name="CreationDate" type="xs:date" />
                                                <xs:attribute name="FileName" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="AssociatedFIMTickets" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:attribute name="FIMNumber" type="xs:string" />
                                                <xs:attribute name="OriginalFlightDate" type="xs:date" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="SoldFlightDetails" type="SegmentInfo_REV" minOccurs="0" />
                                        <xs:element name="ProvisoInformation" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                                <xs:attribute name="ProvisoRateDefinition" type="xs:float" />
                                                <xs:attribute name="PMPParagraph" type="xs:string" />
                                                <xs:attribute name="MPRCheck" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="ChangeAtUsageReason" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:attribute name="Reason" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FareCalculationCharges" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="FareCalculationCharge" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                            <xs:attribute name="ChargeType" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="RefundedAmounts" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RefundedAmountsCouponLevel" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedFareCouponLevel" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="AccountableEntity" type="AccountableEntity_REV"
                                                                            minOccurs="0" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundedTaxesOnCommission" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundedTaxOnCommission" type="VAT_REV" minOccurs="0"
                                                                            maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundedTaxesCouponLevel" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundedTaxCouponLevel" type="Tax_REV" minOccurs="0"
                                                                            maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundedFeesCouponLevel" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundedFeeCouponLevel" type="Fee_REV" minOccurs="0"
                                                                            maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundedSupplementaryCommissions" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundedSupplementaryCommission" type="Commission_REV"
                                                                            minOccurs="0" maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundedRecallCommissions" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundedRecallCommission" type="Commission_REV"
                                                                            minOccurs="0" maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="RefundFeesCouponLevel" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="RefundFeeCouponLevel" type="Fee_REV" minOccurs="0"
                                                                            maxOccurs="unbounded" />
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                            <xs:attribute name="RefundEventNumber" type="xs:integer" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="OriginalValues" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="ProratedFareAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="EMDCouponInformation" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attribute name="ServiceType" type="xs:string" />
                                                <xs:attribute name="NumberOfService" type="xs:integer" />
                                                <xs:attribute name="AttributeGroup" type="xs:string" />
                                                <xs:attribute name="AttributeSubGroup" type="xs:string" />
                                                <xs:attribute name="IndustryCarrierIndicator" type="xs:string" />
                                                <xs:attribute name="FeeOwnerAirline" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CumComReferences" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="Reference" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:attribute name="RuleID" type="xs:string" />
                                                            <xs:attribute name="StartDate" type="xs:date" />
                                                            <xs:attribute name="CommissionType" type="xs:string" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CouponSubsidyInformation" minOccurs="0">
											<xs:complexType>
												<xs:sequence minOccurs="0">
													<xs:element name="Item" minOccurs="0" maxOccurs="unbounded">
														<xs:complexType>
															<xs:sequence minOccurs="0">
																<xs:element name="ItemBreakdownCode" type="xs:string" minOccurs="0"/>
																<xs:element name="IsSubsidyItem" type="xs:string" minOccurs="0"/>
																<xs:element name="SubsidyType" type="xs:string" minOccurs="0"/>
																<xs:element name="SubsidyAmount" type="xs:string" minOccurs="0"/>
															</xs:sequence>
														</xs:complexType>
													</xs:element>
												</xs:sequence>
											</xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                    <xs:attribute name="Number" type="xs:integer" />
                                    <xs:attribute name="ConjunctiveNumber" type="xs:integer" />
                                    <xs:attribute name="DocumentNbr" type="xs:string" />
                                    <xs:attribute name="ConjunctiveDocumentNbr" type="xs:string" />
                                    <xs:attribute name="Status" type="xs:string" />
									<xs:attribute name="StatusLastUpdateDate" type="xs:dateTime" use="optional" />
                                    <xs:attribute name="NotValidBefore" type="xs:date" use="optional" />
                                    <xs:attribute name="NotValidAfter" type="xs:date" use="optional" />
                                    <xs:attribute name="IsCodeshare" type="xs:string" />
                                    <xs:attribute name="IsSurfaceCoupon" type="xs:string" />
                                    <xs:attribute name="ReasonForIssuanceSubCode" type="xs:string" use="optional" />
									<xs:attribute name="EMDRemark" type="xs:string" use="optional" />
                                    <xs:attribute name="ConsumedAtIssuance" type="xs:string" use="optional" />
                                    <xs:attribute name="RFISCDescription" type="xs:string" />
                                    <xs:attribute name="IsRedemptionTicket" type="xs:string" />
                                    <xs:attribute name="DetailedOperationalStatus" type="xs:string" />
                                    <xs:attribute name="IsRevenuePassenger" type="xs:string" />
                                    <xs:attribute name="RefundingCarrier" type="xs:string" />
                                    <xs:attribute name="StatusUpdatedBy" type="xs:string" />
                                    <xs:attribute name="IsExpired" type="xs:string" />
									<xs:attribute name="IsRerouted" type="xs:string" />
									<xs:attribute name="PackageCode" type="xs:string" use="optional" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="RefundedDocument" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="RefundingEntity" type="IssuerInformation_REV" minOccurs="0" />
                                        <xs:element name="RefundedFOP" type="FOP_REV" minOccurs="0" maxOccurs="unbounded" />
                                        <xs:element name="RefundedCoupon" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:attribute name="Number" type="xs:integer" />
                                                <xs:attribute name="ConjunctiveNumber" type="xs:integer" />
                                                <xs:attribute name="ConjunctiveTicketNumber" type="xs:string" />
                                                <xs:attribute name="IsUsedInExpectedRefundCalculation" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FarePaid" type="Fare_REV" minOccurs="0" />
                                        <xs:element name="FareUsed" type="Fare_REV" minOccurs="0" />
                                        <xs:element name="RefundMonetaryInformation" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RefundedFares" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Fare" type="Fare_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedTaxes" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Tax" type="Tax_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedFees" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Fee" type="Fee_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="CommissionRecall" type="Commission_REV" minOccurs="0" />
                                                    <xs:element name="CommissionSupplementary" type="Commission_REV" minOccurs="0" />
                                                    <xs:element name="RefundFee" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Fee" type="Fee_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundFeeCommissions" type="Commission_REV" minOccurs="0"
                                                    maxOccurs="unbounded" />
                                                    <xs:element name="TaxesOnRefundCommission" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="TaxOnRefundCommission" type="VAT_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TaxesOnRefundFee" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="TaxOnRefundFee" type="VAT_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedRemittanceAmount" type="AccountableEntity_REV" minOccurs="0" />
                                                    <xs:element name="RefundedTotalDocumentAmount" type="AccountableEntity_REV" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="ReportingInformation" type="ReportingInformation_REV" minOccurs="0" />
                                        <xs:element name="ExpectedRefundedAmounts" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="ExpectedRefundedFare" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ExpectedRefundedTaxesOnCommission" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExpectedRefundedTaxOnCommission" type="VAT_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ExpectedRefundedTaxes" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExpectedRefundedTax" type="Tax_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ExpectedRefundedFees" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExpectedRefundedFee" type="Fee_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ExpectedSupplementaryCommissions" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExpectedSupplementaryCommission" type="Commission_REV"
                                                                minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ExpectedRecallCommissions" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="ExpectedRecallCommission" type="Commission_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="ADM" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="Fare" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TaxOnCommission" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Tax" type="VAT_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="Taxes" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Tax" type="Tax_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="Fees" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Fee" type="Fee_REV" minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="SupplementaryCommission" type="Commission_REV" minOccurs="0" />
                                                    <xs:element name="StandardCommission" type="Commission_REV" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                    <xs:attribute name="RefundedPrimaryDocumentNbr" type="xs:string" />
                                    <xs:attribute name="IssuanceLocalDate" type="xs:date" />
                                    <xs:attribute name="RefundLocalDate" type="xs:date" use="optional" />
                                    <xs:attribute name="TransmissionControlNumber" type="xs:string" use="optional" />
                                    <xs:attribute name="RoutingType" type="xs:string" use="optional" />
                                    <xs:attribute name="TourCode" type="xs:string" use="optional" />
                                    <xs:attribute name="AirlineAuthority" type="xs:string" use="optional" />
                                    <xs:attribute name="RefundRemarks" type="xs:string" use="optional" />
                                    <xs:attribute name="IsCoverRefund" type="xs:string" />
                                    <xs:attribute name="IsCancelled" type="xs:string" />
                                    <xs:attribute name="IsTaxOnlyRefund" type="xs:string" />
                                    <xs:attribute name="RefundedPaxFirstName" type="xs:string" use="optional" />
                                    <xs:attribute name="RefundedPaxLastName" type="xs:string" use="optional" />
                                    <xs:attribute name="RefundBSR" type="xs:double" use="optional" />
                                    <xs:attribute name="RefundManualRate" type="xs:double" use="optional" />
                                    <xs:attribute name="RefundedCurrency" type="xs:string" use="optional" />
                                    <xs:attribute name="DataRefundIndicator" type="xs:string" use="optional" />
                                    <xs:attribute name="RefundEventNumber" type="xs:integer" />
                                    <xs:attribute name="IsRejected" type="xs:string" default="N" />
                                    <xs:attribute name="WaiverCode" type="xs:string" />
                                    <xs:attribute name="IsPendingValidation" type="xs:string" default="N" />
                                    <xs:attribute name="IsManualRefund" type="xs:string" default="N" />
                                    <xs:attribute name="ReasonForRefund" type="xs:string" />
                                    <xs:attribute name="IsAllRemainingCouponRefunded" type="xs:string" />
                                    <xs:attribute name="CARF" type="xs:string" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="AssociatedTicketInfo" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="AssociatedTicketInfoFOP" type="FOP_REV" minOccurs="0" maxOccurs="unbounded" />
                                    </xs:sequence>
                                    <xs:attribute name="IssuanceDate" type="xs:date" />
                                    <xs:attribute name="TicketDocumentNbr" type="xs:string" />
                                    <xs:attribute name="IsDissociated" type="xs:string" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="RefundedAmounts" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="RefundedAmountsDocumentLevel" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="RefundedTaxesDocumentLevel" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedTaxDocumentLevel" type="Tax_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedFeesDocumentLevel" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedFeeDocumentLevel" type="Fee_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedTaxesOnCommission" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedTaxOnCommission" type="VAT_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundFeesDocumentLevel" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundFeeDocumentLevel" type="Fee_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedFareDocumentLevel" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedRecallCommissions" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedRecallCommission" type="Commission_REV" minOccurs="0"
                                                                maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="RefundedSupplementaryCommissions" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="RefundedSupplementaryCommission" type="Commission_REV"
                                                                minOccurs="0" maxOccurs="unbounded" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                                <xs:attribute name="RefundEventNumber" type="xs:integer" />
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="AmountPaidByCustomer" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="AccountableEntity" type="AccountableEntity_REV" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="DocumentSubsidyInformation" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
										<xs:element name="IsResidentDiscount" type="xs:string" minOccurs="0"/>
										<xs:element name="IsSmallFamilyDiscount" type="xs:string" minOccurs="0"/>
										<xs:element name="IsLargeFamilyDiscount" type="xs:string" minOccurs="0"/>
										<xs:element name="IsDiscardFareResident" type="xs:string" minOccurs="0"/>
										<xs:element name="IsDiscardFareFamily" type="xs:string" minOccurs="0"/>
										<xs:element name="IsDiscardServiceFeeResident" type="xs:string" minOccurs="0"/>
										<xs:element name="IsDiscardServiceFeeFamily" type="xs:string" minOccurs="0"/>
										<xs:element name="AccreditationTypeSRD" type="xs:string" minOccurs="0"/>
										<xs:element name="AccreditationTypeSFD" type="xs:string" minOccurs="0"/>
										<xs:element name="SARAHashCode" type="xs:string" minOccurs="0"/>
										<xs:element name="PassengerName" type="xs:string" minOccurs="0"/>
										<xs:element name="FirstPassengerLastName" type="xs:string" minOccurs="0"/>
										<xs:element name="SecondPassengerLastName" type="xs:string" minOccurs="0"/>
										<xs:element name="IdentificationCardNumber" type="xs:string" minOccurs="0"/>
										<xs:element name="AutonomousCommunityCode" type="xs:string" minOccurs="0"/>
										<xs:element name="ZipCode" type="xs:string" minOccurs="0"/>
										<xs:element name="AgencyChannelName" type="xs:string" minOccurs="0"/>
										<xs:element name="AgreementsCodification" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>
										<xs:element name="TotalSubsidyAmount" type="xs:string" minOccurs="0"/>
										<xs:element name="LargeFamilyIndicator" type="xs:string" minOccurs="0"/>
										<xs:element name="LargeFamilyCardNumber" type="xs:string" minOccurs="0"/>
										<xs:element name="ServiceFeeItem" minOccurs="0">
											<xs:complexType>
												<xs:sequence minOccurs="0">
													<xs:element name="ItemBreakdownCode" type="xs:string" minOccurs="0"/>
													<xs:element name="IsSubsidyItem" type="xs:string" minOccurs="0"/>
													<xs:element name="SubsidyAmountSRD" type="xs:string" minOccurs="0"/>
													<xs:element name="SubsidyAmountSFD" type="xs:string" minOccurs="0"/>
													<xs:element name="AirlineIdentification" type="xs:string" minOccurs="0"/>
													<xs:element name="IssuanceType" type="xs:string" minOccurs="0"/>
													<xs:element name="ServiceFeeIndex" type="xs:string" minOccurs="0"/>
												</xs:sequence>
											</xs:complexType>
										</xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="AdditionalTaxInformation" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
					<xs:element name="Identifier" type="xs:string" minOccurs="0"/>
					<xs:element name="InformationDetails" type="xs:string" minOccurs="0"/>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                        </xs:sequence>
		      <xs:attribute name="InternalId" type="xs:integer" use="optional" />
                        <xs:attribute name="PrimaryDocumentNbr" type="xs:string" use="optional" />
                        <xs:attribute name="Type" type="xs:string" use="optional" />
                        <xs:attribute name="DocumentOperationalStatus" type="xs:string" use="optional" />
                        <xs:attribute name="IssueIndicator" type="xs:string" />
                        <xs:attribute name="TransactionCode" type="xs:string" use="optional" />
                        <xs:attribute name="TransactionType" type="xs:string" use="optional" />
                        <xs:attribute name="NumberOfConjunctiveTickets" type="xs:integer" />
                        <xs:attribute name="ReasonForIssuanceCode" type="xs:string" use="optional" />
						<xs:attribute name="EMDRemark" type="xs:string" use="optional" />
						<xs:attribute name="FullRouting" type="xs:string" use="optional" />
                        <xs:attribute name="ValidatingCarrier" type="xs:string" />
                        <xs:attribute name="ReasonForIssuanceDescription" type="xs:string" use="optional" />
                        <xs:attribute name="DateOfIssuance" type="xs:date" use="optional" />
                        <xs:attribute name="ValidatingAirlineAllianceCode" type="xs:string" />
                        <xs:attribute name="OriginalIssueInfoFreeFlow" type="xs:string" />
                        <xs:attribute name="Code" type="xs:string" />
                        <xs:attribute name="AcquisitionType" type="xs:string" use="optional" />
                        <xs:attribute name="InvoluntaryIndicator" type="xs:string" />
						<xs:attribute name="IsLafAppliedIndicator" type="xs:string" />
						<xs:attribute name="IsRedemptionTicket" type="xs:string" />
						<xs:attribute name="IsRedemptionWithFareTicket" type="xs:string" />
						<xs:attribute name="IsScheduleChange" type="xs:string" />
            			<xs:attribute name="AgencyName" type="xs:string" use="optional" />
            			<xs:attribute name="AgencyGroupName" type="xs:string" use="optional" />
                    </xs:complexType>
                </xs:element>
                <xs:element name="FIM" minOccurs="0">
                    <xs:complexType>
                        <xs:sequence minOccurs="0">
                            <xs:element name="FIMItinerary" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="OldItinerary" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="OperatingCarrierCode" type="xs:string"
                                                    minOccurs="0" />
                                                    <xs:element name="OriginalFlightNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OriginalFlightDate" type="xs:date" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CouponMonetaryInformation" type="CouponAmounts_REV" minOccurs="0" />
                                        <xs:element name="InterlineBillingInfo" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="BillingLevel" type="xs:string" minOccurs="0" />
                                                    <xs:element name="BillingStatus" type="xs:string" minOccurs="0" />
                                                    <xs:element name="BillingPeriod" type="BillingPeriod_REV" minOccurs="0" />
                                                    <xs:element name="InvoiceNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="RejectionMemoNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="BillingDate" type="xs:date" minOccurs="0" />
                                                    <xs:element name="SourceCode" type="xs:string" minOccurs="0" />
                                                    <xs:element name="NextReplyDeadline" type="xs:date" minOccurs="0" />
                                                    <xs:element name="ISIDECFileName" type="xs:string" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FIMFlightTicket" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="PAXDocNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OriginalTicketNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OriginalCouponNumber" type="xs:integer" minOccurs="0" />
                                                    <xs:element name="TransactionCode" type="xs:string" minOccurs="0" />
                                                    <xs:element name="PAXFirstName" type="xs:string" minOccurs="0" />
                                                    <xs:element name="PAXLastName" type="xs:string" minOccurs="0" />
                                                    <xs:element name="PassengerType" type="xs:string" minOccurs="0" />
                                                    <xs:element name="OriginalFareBasis" type="xs:string" minOccurs="0" />
                                                    <xs:element name="FIMFlightCoupon" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="NewCabinClass" type="xs:string" minOccurs="0" />
																<xs:element name="OriginalCouponNumber" type="iata_ct:Numeric0to99" minOccurs="0" />
                                                                <xs:element name="CouponMonetaryInformation" type="CouponAmounts_REV"
                                                                minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="FIMEMDTicket" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="PAXDocNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="TicketNumber" type="xs:string" minOccurs="0" />
                                                    <xs:element name="CouponNumber" type="xs:integer" minOccurs="0" />
                                                    <xs:element name="TransactionCode" type="xs:string" minOccurs="0" />
                                                    <xs:element name="PAXLastName" type="xs:string" minOccurs="0" />
                                                    <xs:element name="EMDCoupon" minOccurs="0" maxOccurs="unbounded">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="EMDCouponMonetaryInfo" type="CouponAmounts_REV" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                    <xs:attribute name="FIMType" type="xs:string" />
                                    <xs:attribute name="FIMNumber" type="xs:string" use="optional" />
                                    <xs:attribute name="FIMBilledCarrierCode" type="xs:string" />
                                    <xs:attribute name="NumberOfPax" type="xs:integer" />
                                    <xs:attribute name="ReasonOfIssuance" type="xs:string" />
                                    <xs:attribute name="PlaceOfInterruption" type="xs:string" />
                                    <xs:attribute name="CouponNumber" type="xs:integer" />
                                    <xs:attribute name="CarrierCode" type="xs:string" />
                                    <xs:attribute name="BoardPoint" type="xs:string" />
                                    <xs:attribute name="OffPoint" type="xs:string" />
                                    <xs:attribute name="FlightNumber" type="xs:string" />
                                    <xs:attribute name="FlightDate" type="xs:date" />
                                    <xs:attribute name="CreationDate" type="xs:date" />
                                </xs:complexType>
                            </xs:element>
                        </xs:sequence>
                    </xs:complexType>
                </xs:element>
                <xs:element name="AgencyMemo" minOccurs="0">
                    <xs:complexType>
                        <xs:sequence minOccurs="0">
                            <xs:element name="MemoType" type="xs:string" />
                            <xs:element name="Status" type="xs:string" minOccurs="0" />
                            <xs:element name="LastUpdateDate" type="xs:dateTime" minOccurs="0" />
                            <xs:element name="MemoNumber" type="xs:string" />
                            <xs:element name="DateOfIssue" type="xs:date" minOccurs="0" />
                            <xs:element name="DisputeDate" type="xs:dateTime" minOccurs="0" />
							<xs:element name="DisputeApprovedDate" type="xs:date" minOccurs="0" />
							<xs:element name="DisputeRejectedDate" type="xs:date" minOccurs="0" />
                            <xs:element name="IATANumber" type="xs:string" minOccurs="0" />
                            <xs:element name="ISOCountryCode" type="xs:string" minOccurs="0" />
                            <xs:element name="OfficeID" minOccurs="0">
                                <xs:simpleType>
                                    <xs:restriction base="xs:string" />
                                </xs:simpleType>
                            </xs:element>
                            <xs:element name="AgentSine" type="xs:string" minOccurs="0" />
                            <xs:element name="BillingPeriod" type="BillingPeriod_REV" minOccurs="0" />
                            <xs:element name="AirlineContact" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="ContactName" type="xs:string" minOccurs="0" />
                                        <xs:element name="PhoneFax" type="xs:string" minOccurs="0" />
                                        <xs:element name="Email" type="xs:string" minOccurs="0" />
                                        <xs:element name="OwnerTeam" type="xs:string" minOccurs="0" />
                                        <xs:element name="GroupingCode" type="xs:string" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="ReasonForMemoInformation" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="ReasonForMemoCode" type="xs:string" minOccurs="0" />
                                        <xs:element name="ReasonForMemoText" type="xs:string" minOccurs="0" />
                                        <xs:element name="ReasonFullComment" type="xs:string" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="RelatedTransactionType" type="xs:string" minOccurs="0" />
                            <xs:element name="RelatedDocument" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="DocumentNumber" type="xs:string" minOccurs="0"/>
                                        <xs:element name="DocumentType" type="xs:string" minOccurs="0" />
                                        <xs:element name="DateOfIssue" type="xs:date" minOccurs="0" />
                                        <xs:element name="PassengerName" type="xs:string" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="MonetaryInformation" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="CurrencyCode" type="xs:string" minOccurs="0" />
                                        <xs:element name="RemittanceAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="SettledAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="MonetaryDetails" minOccurs="0" maxOccurs="unbounded">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="FareAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TotalTaxAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="TaxAmount" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="TaxDetails" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="Tax" minOccurs="0" maxOccurs="unbounded">
                                                                                <xs:complexType>
                                                                                    <xs:sequence minOccurs="0">
                                                                                        <xs:element name="TaxType" type="xs:string" minOccurs="0" />
                                                                                        <xs:element name="Amount" minOccurs="0">
                                                                                            <xs:complexType>
                                                                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                                            </xs:complexType>
                                                                                        </xs:element>
                                                                                    </xs:sequence>
                                                                                </xs:complexType>
                                                                            </xs:element>
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="CommissionAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="SPAMAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TOCAAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Amount" minOccurs="0">
                                                                    <xs:complexType>
                                                                        <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                    </xs:complexType>
                                                                </xs:element>
                                                                <xs:element name="TOCAType" type="xs:string" minOccurs="0" />
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="CPAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="MFAmount" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                                <xs:attribute name="Type" type="xs:string" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="NewRemittanceAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CumulatedDisputeApproved" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="CumulativePaidAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="AccountedAmountDiffBudget" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="BalanceBudgetNumber" type="xs:string" minOccurs="0" />
                        </xs:sequence>
                    </xs:complexType>
                </xs:element>
                <xs:element name="InterlineMemo" minOccurs="0">
                    <xs:complexType>
                        <xs:sequence minOccurs="0">
                            <xs:element name="MemoType" type="xs:string" minOccurs="0" />
                            <xs:element name="MemoNumber" type="xs:string" />
                            <xs:element name="ReasonCode" type="xs:string" minOccurs="0" />
                            <xs:element name="From" type="xs:string" />
                            <xs:element name="To" type="xs:string" />
                            <xs:element name="MemoStatus" type="xs:string" minOccurs="0" />
                            <xs:element name="RejectionStage" type="xs:integer" minOccurs="0" />
                            <xs:element name="InvoiceNumber" type="xs:string" minOccurs="0" />
                            <xs:element name="BillingPeriod" type="BillingPeriod_REV" minOccurs="0" />
                            <xs:element name="OriginalInvoiceNumber" type="xs:string" minOccurs="0" />
                            <xs:element name="OriginalInvoiceBillingDate" type="xs:date" minOccurs="0" />
                            <xs:element name="OriginalBillingPeriod" type="BillingPeriod_REV" minOccurs="0" />
                            <xs:element name="CurrencyOfBilling" type="xs:string" minOccurs="0" />
                            <xs:element name="ROEfromListingToBilling" type="xs:decimal" minOccurs="0" />
                            <xs:element name="FIMBillingCreditMemoNumber" type="xs:string" minOccurs="0" />
                            <xs:element name="FIMCouponNumber" type="xs:integer" minOccurs="0" />
                            <xs:element name="FIM.BM.CMIndicator" type="xs:string" minOccurs="0" />
                            <xs:element name="TotalMemoAmount" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="TotalNetAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalGrossAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="GrossAmountBilled" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="GrossAmountAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="GrossDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalTaxAmount" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="TotalTaxAmountBilled" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TotalTaxAmountAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TotalTaxAmountDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="TaxDetails" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:sequence minOccurs="0">
                                                                <xs:element name="Tax" minOccurs="0" maxOccurs="unbounded">
                                                                    <xs:complexType>
                                                                        <xs:sequence minOccurs="0">
                                                                            <xs:element name="TaxCode" type="xs:string" minOccurs="0" />
                                                                            <xs:element name="TaxAmountBilled" minOccurs="0">
                                                                                <xs:complexType>
                                                                                    <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                                </xs:complexType>
                                                                            </xs:element>
                                                                            <xs:element name="TaxAmountAccepted" minOccurs="0">
                                                                                <xs:complexType>
                                                                                    <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                                </xs:complexType>
                                                                            </xs:element>
                                                                            <xs:element name="TaxAmountDifference" minOccurs="0">
                                                                                <xs:complexType>
                                                                                    <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                                                </xs:complexType>
                                                                            </xs:element>
                                                                        </xs:sequence>
                                                                    </xs:complexType>
                                                                </xs:element>
                                                            </xs:sequence>
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalISC" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="ISCRateAllowed" type="Rate" minOccurs="0" />
                                                    <xs:element name="ISCRateAccepted" type="Rate" minOccurs="0" />
                                                    <xs:element name="ISCAmountAllowed" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ISCAmountAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="ISCAmountDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalOtherCommission" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="OtherCommissionRateAllowed" type="Rate" minOccurs="0" />
                                                    <xs:element name="OtherCommissionRateAccepted" type="Rate" minOccurs="0" />
                                                    <xs:element name="OtherCommissionAllowed" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="OtherCommissionAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="OtherCommissionDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalHandlingFee" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="HandlingFeeAllowed" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="HandlingFeeAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="HandlingFeeDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalUATP" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="UATPRateAllowed" type="Rate" minOccurs="0" />
                                                    <xs:element name="UATPRateAccepted" type="Rate" minOccurs="0" />
                                                    <xs:element name="UATPChargeAllowed" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="UATPChargeAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="UATPChargeDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                        <xs:element name="TotalVAT" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="VATAmountBilled" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="VATAmountAccepted" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                    <xs:element name="VATAmountDifference" minOccurs="0">
                                                        <xs:complexType>
                                                            <xs:attributeGroup ref="CurrencyAmountGroup_REV" />
                                                        </xs:complexType>
                                                    </xs:element>
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="RejMemoOrigInfo" minOccurs="0">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="OriginalRejectionMemoNumber" type="xs:string" minOccurs="0" />
                                        <xs:element name="OriginalRejectionStage" type="xs:integer" minOccurs="0" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="CurrencyOfListing" type="xs:string" minOccurs="0" />
                            <xs:element name="CreationDate" type="xs:date" minOccurs="0" />
                            <xs:element name="Coupon" minOccurs="0" maxOccurs="unbounded">
                                <xs:complexType>
                                    <xs:sequence minOccurs="0">
                                        <xs:element name="CouponAmounts" type="CouponAmounts_REV" minOccurs="0" />
                                        <xs:element name="InterlineDetails" minOccurs="0">
                                            <xs:complexType>
                                                <xs:sequence minOccurs="0">
                                                    <xs:element name="InterlineInformation" type="InterlineInformation_REV" minOccurs="0" />
                                                    <xs:element name="OriginalInterlineInformation" type="InterlineInformation_REV" minOccurs="0" />
                                                </xs:sequence>
                                            </xs:complexType>
                                        </xs:element>
                                    </xs:sequence>
                                    <xs:attribute name="Number" type="xs:integer" />
                                    <xs:attribute name="ConjunctiveNumber" type="xs:integer" />
                                    <xs:attribute name="DocumentNbr" type="xs:string" />
                                    <xs:attribute name="ConjunctiveDocumentNbr" type="xs:string" />
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="InterlineCorrespondence" type="InterlineCorrespondence_REV" minOccurs="0" />
                            <xs:element name="InterlineDirection" type="xs:string" minOccurs="0" />
                            <xs:element name="SourceCode" type="xs:string" minOccurs="0" />
                            <xs:element name="SubmissionDeadline" type="xs:date" minOccurs="0" />
                            <xs:element name="Remark" type="xs:string" minOccurs="0" />
                        </xs:sequence>
                    </xs:complexType>
                </xs:element>
            </xs:choice>
        </xs:sequence>
    </xs:complexType>
</xs:schema>
