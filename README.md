# QA-Automation-Test
import { test, expect } from '@playwright/test';

test('test', async ({ page }) => {
  await page.goto('http://192.168.100.103:8001/bepza_uat/login/auth');
  await page.getByRole('textbox', { name: 'User name...' }).click();
  await page.getByRole('textbox', { name: 'User name...' }).fill('chairman');
  await page.getByRole('textbox', { name: 'Password..' }).click();
  await page.getByRole('textbox', { name: 'Password..' }).fill('abcd1234');
  await page.getByRole('button', { name: 'Sign In' }).click();
  await page.getByRole('link', { name: ' General Report' }).click();
  await page.getByRole('combobox', { name: 'Select One' }).click();
  await page.locator('#zoneId').selectOption('4');
  await page.locator('#fromDate').click();
  await page.getByRole('columnheader', { name: '«' }).click();
  await page.locator('#fromDate').dblclick();
  await page.locator('#fromDate').click();
  await page.locator('#fromDate').click();
  await page.getByRole('cell', { name: '1' }).first().click();
  await page.locator('#toDate').click();
  await page.getByRole('columnheader', { name: '«' }).click();
  await page.locator('#toDate').dblclick();
  await page.locator('#toDate').click();
  await page.locator('#toDate').click();
  await page.getByRole('cell', { name: '31' }).click();
  const page1Promise = page.waitForEvent('popup');
  await page.getByRole('button', { name: ' Generate Report' }).click();
  const page1 = await page1Promise;
});
