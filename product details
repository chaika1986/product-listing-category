import { baseURL, revealAllPage, testCase, visitWithCookie } from 'support/utils/commands';
import { city } from 'support/utils/selectors';
import { productListingCategoryLinks } from 'support/productListing/links';
import { takeInfoFromListing } from 'support/productListing/commands';
import { productListing } from 'support/productListing/selectors';

describe('chayka-3 - Получить консультацию, КТ, кухня', () => {
    testCase(() => {
        it('Получить консультацию', () => {
            visitWithCookie(baseURL() + productListingCategoryLinks.kuhni, city.Moscow);
            takeInfoFromListing(0).then((listing) => {
                cy.get(productListing.item)
                    .first()
                    .clickAndWait()
                    .then(() => {
                        revealAllPage(1000);
                        cy.contains('have.product-details', 'Заказать проект');
                        cy.get.should('be.visible');
                    });
            });
        });
    });
});
